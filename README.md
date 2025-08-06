#🌾 Fasal Saarthi: Kushal Kisan - AI-Powered Crop Recommendation System
A cutting-edge, machine learning-powered system designed to empower farmers by recommending the most suitable crops for their land, thereby maximizing agricultural yield. This project leverages IBM Cloud's Watsonx.ai Studio to provide intelligent, data-driven decisions.

#Deployed Model Endpoint: https://au-syd.ml.cloud.ibm.com/ml/v4/deployments/6e5c5f4f-6361-4659-bc73-e8e6ce7b716a/predictions?version=2021-05-01

#🌟 Key Features
Intelligent Crop Recommendations: Provides precise, data-backed suggestions for optimal crop selection based on environmental and soil conditions.

Comprehensive Parameter Analysis: Utilizes critical factors including Nitrogen (N), Phosphorous (P), Potassium (K) ratios, temperature, humidity, pH value, and rainfall.

Automated Machine Learning: Built and deployed efficiently using IBM Watsonx.ai Studio's powerful AutoAI capabilities, streamlining the entire ML pipeline.

High-Confidence Predictions: Delivers reliable crop suggestions to aid farmers in making informed decisions.

#🛠️ Tech Stack
Cloud Platform: IBM Cloud

AI/ML Services: IBM Watsonx.ai Studio, AutoAI

Programming Languages (Client Interaction): Python, Java, JavaScript, Scala

Data Handling: Pandas (implied by AutoAI process)

Version Control: Git, GitHub

#📊 Dataset
The project utilizes a comprehensive dataset sourced from the Indian Chamber of Food and Agriculture (ICFA). This dataset was created by augmenting existing rainfall, climate, and fertilizer data specific to India.

Key Data Fields:

N: Nitrogen content ratio in soil

P: Phosphorous content ratio in soil

K: Potassium content ratio in soil

temperature: Temperature in degrees Celsius

humidity: Relative humidity in %

ph: pH value of the soil

rainfall: Rainfall in mm

label: The recommended crop (target variable for prediction)

🚀 How to Interact with the Deployed Model
The crop recommendation model is deployed on IBM Cloud and can be accessed via its public API endpoint. Below are code snippets in various languages demonstrating how to obtain an IAM token and make predictions.

Prerequisites:

An IBM Cloud account.

An IBM Cloud API Key. You can retrieve this from your IBM Cloud account settings: IBM Cloud API Keys

Deployed Model Endpoint:
https://au-syd.ml.cloud.ibm.com/ml/v4/deployments/6e5c5f4f-6361-4659-bc73-e8e6ce7b716a/predictions?version=2021-05-01

Remember to replace <your API key>, [array_of_input_fields], [array_of_values_to_be_scored], and [another_array_of_values_to_be_scored] with your actual data.

Python Example
import requests

# NOTE: you must manually set API_KEY below using information retrieved from your IBM Cloud account
API_KEY = "<your API key>"
token_response = requests.post('https://iam.cloud.ibm.com/identity/token', data={"apikey": API_KEY, "grant_type": 'urn:ibm:params:oauth:grant-type:apikey'})
mltoken = token_response.json()["access_token"]

header = {'Content-Type': 'application/json', 'Authorization': 'Bearer ' + mltoken}

# NOTE: manually define and pass the array(s) of values to be scored
payload_scoring = {"input_data": [
	{
		"fields": [array_of_input_fields], # e.g., ["N", "P", "K", "temperature", "humidity", "ph", "rainfall"]
		"values": [[array_of_values_to_be_scored]] # e.g., [[90, 42, 43, 20.88, 82.00, 6.50, 202.94]]
	}
]}

response_scoring = requests.post(
    'https://private.au-syd.ml.cloud.ibm.com/ml/v4/deployments/6e5c5f4f-6361-4659-bc73-e8e6ce7b716a/predictions?version=2021-05-01',
    json=payload_scoring,
    headers={'Authorization': 'Bearer ' + mltoken}
)

print("Scoring response")
try:
    print(response_scoring.json())
except ValueError:
    print(response_scoring.text)
except Exception as e:
    print(f"An unexpected error occurred: {e}")

Java Example
import java.io.*;
import java.net.HttpURLConnection;
import java.net.URL;
import java.nio.charset.StandardCharsets;

public class HttpClientTest {
	public static void main(String[] args) throws IOException {

		// NOTE: you must manually set API_KEY below using information retrieved from your IBM Cloud account.
		String API_KEY = "<your API key>";

		HttpURLConnection tokenConnection = null;
		HttpURLConnection scoringConnection = null;
		BufferedReader tokenBuffer = null;
		BufferedReader scoringBuffer = null;
		try {
			// Getting IAM token
			URL tokenUrl = new URL("https://iam.cloud.ibm.com/identity/token?grant_type=urn:ibm:params:oauth:grant-type:apikey&apikey=" + API_KEY);
			tokenConnection = (HttpURLConnection) tokenUrl.openConnection();
			tokenConnection.setDoInput(true);
			tokenConnection.setDoOutput(true);
			tokenConnection.setRequestMethod("POST");
			tokenConnection.setRequestProperty("Content-Type", "application/x-www-form-urlencoded");
			tokenConnection.setRequestProperty("Accept", "application/json");

			if (tokenConnection.getResponseCode() == 200) { // Successful response
				tokenBuffer = new BufferedReader(new InputStreamReader(tokenConnection.getInputStream()));
			} else { // Error response
				tokenBuffer = new BufferedReader(new InputStreamReader(tokenConnection.getErrorStream()));
			}

            String line;
			StringBuffer jsonString = new StringBuffer();
            while ((line = tokenBuffer.readLine()) != null) {
                jsonString.append(line);
            }
            System.out.println("Token response body:\n" + jsonString);

			// Scoring request
			URL scoringUrl = new URL("https://private.au-syd.ml.cloud.ibm.com/ml/v4/deployments/6e5c5f4f-6361-4659-bc73-e8e6ce7b716a/predictions?version=2021-05-01");
			String iam_token = "Bearer " + jsonString.toString().split(":")[1].split("\"")[1];
			scoringConnection = (HttpURLConnection) scoringUrl.openConnection();
			scoringConnection.setDoInput(true);
			scoringConnection.setDoOutput(true);
			scoringConnection.setRequestMethod("POST");
			scoringConnection.setRequestProperty("Accept", "application/json");
			scoringConnection.setRequestProperty("Authorization", iam_token);
			scoringConnection.setRequestProperty("Content-Type", "application/json; charset=UTF-8");
			OutputStreamWriter writer = new OutputStreamWriter(scoringConnection.getOutputStream(), "UTF-8");

			// NOTE: manually define and pass the array(s) of values to be scored
			String payload = """
			{\"input_data\": [
				{
					\"fields\": [array_of_input_fields], // e.g., \"N\", \"P\", \"K\", \"temperature\", \"humidity\", \"ph\", \"rainfall\"
					\"values\": [[array_of_values_to_be_scored]] // e.g., [[90, 42, 43, 20.88, 82.00, 6.50, 202.94]]
				}
			]}""";

			writer.write(payload);
			writer.close();

			if (scoringConnection.getResponseCode() == 200) { // Successful response
				scoringBuffer = new BufferedReader(new InputStreamReader(scoringConnection.getInputStream()));
			} else { // Error response
				scoringBuffer = new BufferedReader(new InputStreamReader(scoringConnection.getErrorStream()));
			}

            String lineScoring;
			StringBuffer jsonStringScoring = new StringBuffer();
            while ((lineScoring = scoringBuffer.readLine()) != null) {
                jsonStringScoring.append(lineScoring);
            }
            System.out.println("Scoring response body:\n" + jsonStringScoring);
		} catch (IOException e) {
			System.out.println("The request was not valid.");
			System.out.println(e.getMessage());
		}
		finally {
			if (tokenConnection != null) {
				tokenConnection.disconnect();
			}
			if (tokenBuffer != null) {
				tokenBuffer.close();
			}
			if (scoringConnection != null) {
				scoringConnection.disconnect();
			}
			if (scoringBuffer != null) {
				scoringBuffer.close();
			}
		}
	}
}

JavaScript Example
const XMLHttpRequest = require("xmlhttprequest").XMLHttpRequest;

// NOTE: you must manually enter your API_KEY below using information retrieved from your IBM Cloud account
const API_KEY = "<your API key>";

const req = new XMLHttpRequest();
const oReq = new XMLHttpRequest();

function getToken(errorCallback, loadCallback) {
	req.addEventListener("load", loadCallback);
	req.addEventListener("error", errorCallback);
	req.open("POST", "https://iam.cloud.ibm.com/identity/token");
	req.setRequestHeader("Content-Type", "application/x-www-form-urlencoded");
	req.setRequestHeader("Accept", "application/json");
	req.send("grant_type=urn:ibm:params:oauth:grant-type:apikey&apikey=" + API_KEY);
}

function apiPost(scoring_url, token, payload, loadCallback, errorCallback) {
	oReq.addEventListener("load", loadCallback);
	oReq.addEventListener("error", errorCallback);
	oReq.open("POST", scoring_url);
	oReq.setRequestHeader("Accept", "application/json");
	oReq.setRequestHeader("Authorization", "Bearer " + token);
	oReq.setRequestHeader("Content-Type", "application/json;charset=UTF-8");
	oReq.send(payload);
}

getToken((err) => console.log("An error occurred submitting the request."), () => {
	let tokenResponse;
	try {
		tokenResponse = JSON.parse(req.responseText);
	} catch(ex) {
		console.log("An error occurred parsing the token response.");
		return;
	}
	// NOTE: manually define and pass the array(s) of values to be scored
	const payload = `{"input_data": [
		{
			"fields": [array_of_input_fields], // e.g., ["N", "P", "K", "temperature", "humidity", "ph", "rainfall"]
			"values": [[array_of_values_to_be_scored]] // e.g., [[90, 42, 43, 20.88, 82.00, 6.50, 202.94]]
		}
	]}`;

	const scoring_url = "https://private.au-syd.ml.cloud.ibm.com/ml/v4/deployments/6e5c5f4f-6361-4659-bc73-e8e6ce7b716a/predictions?version=2021-05-01";
	apiPost(scoring_url, tokenResponse.access_token, payload, function (resp) {
		let parsedPostResponse;
		try {
			parsedPostResponse = JSON.parse(oReq.responseText);
		} catch (ex) {
			console.log("An error occurred parsing the scoring response.");
			return;
		}
		console.log("Scoring response");
		console.log(JSON.stringify(parsedPostResponse, null, "  "));
	}, function (error) {
		console.log(error);
	});
});

Scala Example
import sttp.client4.quick.*
import scala.util.{Success, Failure}
import java.util.Base64
import java.nio.charset.StandardCharsets
import play.api.libs.json.*

@main def main() = {
	// NOTE: you must manually set API_KEY below using information retrieved from your IBM Cloud account
	val API_KEY = "<your API key>"

	// Get IAM service token
	val iam_url = uri"https://iam.cloud.ibm.com/identity/token?grant_type=urn:ibm:params:oauth:grant-type:apikey&apikey=$API_KEY"
	val iam_response = quickRequest.post(iam_url).header("Content-Type", "application/x-www-form-urlencoded").header("Accept",
		"application/json").send()
	val iamtoken_json: JsValue = Json.parse(iam_response.body)

	val iamtoken = (iamtoken_json \ "access_token").asOpt[String] match {
		case Some(x) => x
		case None => ""
	}

	// NOTE: manually define and pass list of values to be scored
	val payload_scoring = Json.stringify(Json.obj("input_data" -> Json.arr(Json.obj(
		"fields" -> Json.arr(list_of_input_fields), // e.g., "N", "P", "K", "temperature", "humidity", "ph", "rainfall"
		"values" -> Json.arr(Json.arr(list_of_values_to_be_scored)) // e.g., Json.arr(90, 42, 43, 20.88, 82.00, 6.50, 202.94)
	))))

	val scoring_url = uri"https://private.au-syd.ml.cloud.ibm.com/ml/v4/deployments/6e5c5f4f-6361-4659-bc73-e8e6ce7b716a/predictions?version=2021-05-01"

	val response_scoring = quickRequest.post(scoring_url).body(payload_scoring).header("Content-Type",
		"application/json").header("Authorization", "Bearer " + iamtoken).send()
	println("scoring response")
	println(response_scoring.body)
}

🧑‍💻 Contact
PRAKHAR SHARMA

LinkedIn: linkedin.com/in/prakhar-sharma-btech

GitHub: github.com/prak05

Email: praksediting5@edunetmail.com
