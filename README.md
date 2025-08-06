# Fasal Saarthi: AI-Powered Crop Recommendation

## An Intelligent System to Empower Farmers and Maximize Agricultural Yield

### ✨ Project Overview
Fasal Saarthi: Kushal Kisan is an intelligent crop recommendation system designed to empower farmers with data-driven insights. Acting as a "Crop Companion" (Fasal Saarthi), it provides accurate, data-backed suggestions for the most suitable crops to cultivate. By fostering "Skilled Farmers" (Kushal Kisan) through reliable predictions, the system aims to promote sustainable and productive agriculture.

### 💡 Key Features
* **Intelligent Crop Recommendations:** Provides optimal crop suggestions based on a comprehensive analysis of soil and environmental data.
* **Comprehensive Parameter Analysis:** Utilizes key agricultural metrics including soil nutrients (N, P, K), temperature, humidity, pH, and rainfall.
* **Automated ML Pipeline:** The machine learning pipeline was efficiently built and deployed using the automated services of IBM Watsonx.ai Studio's AutoAI.
* **High-Confidence Predictions:** Delivers reliable crop suggestions with a high degree of confidence, enabling farmers to make informed decisions.
* **API-First Design:** The model is deployed with a public endpoint, making it easily accessible for integration into various applications.

### 🛠️ Technologies & Tools
* **AI/ML Platform:** IBM Watsonx.ai Studio
* **Automated Machine Learning:** AutoAI
* **Cloud Infrastructure:** IBM Cloud
* **Programming Language:** Python (for data processing and core logic)
* **API Client Code:** Python, Java, JavaScript, Scala (for model interaction)
* **Version Control:** GitHub

### 📊 Dataset
The project is trained on a comprehensive dataset from the Indian Chamber of Food and Agriculture (ICFA), which combines crucial information on rainfall, climate, and fertilizer use across India.

The dataset includes the following key fields:
* **N:** Nitrogen content ratio in the soil.
* **P:** Phosphorous content ratio in the soil.
* **K:** Potassium content ratio in the soil.
* **temperature:** Average temperature in Celsius.
* **humidity:** Relative humidity in percentage.
* **ph:** The pH value of the soil.
* **rainfall:** Rainfall amount in millimeters.
* **label:** The target variable representing the recommended crop.

### 🚀 Getting Started
To interact with the deployed model or explore the project's assets, you will need an IBM Cloud account with access to Watsonx.ai Studio.

**Deployed Model Endpoint:**
The public endpoint for the deployed crop recommendation model can be accessed here:
`https://au-syd.ml.cloud.ibm.com/ml/v4/deployments/6e5c5f4f-6361-4659-bc73-e8e6ce7b716a/predictions?version=2021-05-01`

**API Interaction:**
The repository contains example client code snippets in Python, Java, JavaScript, and Scala. Remember to replace the placeholder `<your API key>` with your actual IBM Cloud API key to authenticate and make predictions.

#### Python Example
<details><summary>Click to view Python code</summary>
<br>
<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI0MDAiIGhlaWdodD0iMTUwIiB2aWV3Qm94PSIwIDAgNDAwIDE1MCI+CiAgPHJlY3Qgd2lkdGg9IjQwMCIgaGVpZ2h0PSIxNTAiIHJ4PSI4IiBmaWxsPSIjZjVmNWY1IiBzdHJva2U9IiNjY2MiIHN0cm9va2Utd2lkdGg9IjEiLz4KICA8dGV4dCB4PSIyMCIgeT0iMzUiIGZvbnQtZmFtaWx5PSJtb25vc3BhY2UiIGZvbnQtc2l6ZT0iMTQiIGZpbGw9IiMzMzMiPgogICAgPHRzcGFuIHg9IjIwIiBkeT0iMS4yZW0iIGZpbGw9IiMwMDdiZmYiPmltcG9ydDwvdHNwYW4+PHRzcGFuIHg9IjcwIiBkeT0iMCIgZmlsbD0iIzMzMyI+IHJlcXVlc3RzPC90c3Bhbj4KICAgIDx0c3BhbiB4PSIyMCIgZHk9IjEuNWVtIiBmaWxsPSIjMDA3YmZmIj4jIEV4YW1wbGUgZm9yIFB5dGhvbjwvdHNwYW4+CiAgICA8dHNwYW4geD0iMjAiIGR5PSIxLjVlbSIgZmlsbD0iIzAwN2JmZiI+YXBpX2tleTwvdHNwYW4+PHRzcGFuIHg9IjkwIiBkeT0iMCIgZmlsbD0iIzMzMyI+ID0gPC90c3Bhbj48dHNwYW4geD0iMTEwIiBkeT0iMCIgZmlsbD0iI2EwYTBhMCI+IiZsdDt5b3VyIEFQSSBrZXkmZ3Q7Ijx0c3BhbiB4PSIyNjAiIGR5PSIwIiBmaWxsPSIjMzMzIj47PC90c3Bhbj4KICAgIDx0c3BhbiB4PSIyMCIgZHk9IjEuNWVtIiBmaWxsPSIjMDA3YmZmIj51cmw8L3RzcGFuPjx0c3BhbiB4PSI5MCIgZHk9IjAiIGZpbGw9IiMzMzMiPiA9IDwvdHNwYW4+PHRzcGFuIHg9IjExMCIgZHk9IjAiIGZpbGw9IiNhMGEwYTAiPiJodHRwczovL2F1LXN5ZC5tbC5jbG91ZC5pYm0uY29tL21sL3Y0L2RlcGxveW1lbnRzLzYlZTUlYzUlZjRmLTYzNjEtNDY1OS1iYzczLWU4ZTZjZTdiNzE2YS9wcmVkaWN0aW9ucz92ZXJzaW9uPTIwMjEtMDUtMDEiPC90c3Bhbj4KICAgIDx0c3BhbiB4PSIyMCIgZHk9IjEuNWVtIiBmaWxsPSIjMDA3YmZmIj5oZWFkZXJzPC90c3Bhbj48dHNwYW4geD0iOTAiIGR5PSIwIiBmaWxsPSIjMzMzIj4gPSA8L3RzcGFuPjx0c3BhbiB4PSIxMTAiIGR5PSIwIiBmaWxsPSIjMDA3YmZmIj57J0NvbnRlbnQtVHlwZSc8L3RzcGFuPjx0c3BhbiB4PSIyMCIgZHk9IjEuNWVtIiBmaWxsPSIjMzMzIj4gICAgJ2FwcGxpY2F0aW9uL2pzb24nLCAnQXV0aG9yaXphdGlvbic6IGYmIzgyMjA7QmVhcmVyIHthcGlfa2V5fSYjODIyMTs7fTwvdHNwYW4+CiAgICA8dHNwYW4geD0iMjAiIGR5PSIxLjVlbSIgZmlsbD0iIzAwN2JmZiI+IyBTYW1wbGUgZGF0YTwvdHNwYW4+CiAgICA8dHNwYW4geD0iMjAiIGR5PSIxLjVlbSIgZmlsbD0iIzAwN2JmZiI+cGF5bG9hZDwvdHNwYW4+PHRzcGFuIHg9IjkwIiBkeT0iMCIgZmlsbD0iIzMzMyI+ID0geyAnc3VwZXJkYXRhX2lucHV0JzogWydGcm9tJ10sICdhZ2VzJzogWydMbyJdfTwvdHNwYW4+CiAgICA8dHNwYW4geD0iMjAiIGR5PSIxLjVlbSIgZmlsbD0iIzAwN2JmZiI+cmVzcG9uc2U8L3RzcGFuPjx0c3BhbiB4PSI5MCIgZHk9IjAiIGZpbGw9IiMzMzMiPiA9IHJlcXVlc3RzLnBvc3QodXJsLCBqdXN0c3BhbiB4PSIxNDgiIGR5PSIwIiBmaWxsPSIjMzMzIj46cGF5bG9hZCwgaGVhZGVycyk8L3RzcGFuPjwvdGV4dD4KPC9zdmc+">
</details>

#### Java Example
<details><summary>Click to view Java code</summary>
<br>
<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI0MDAiIGhlaWdodD0iMTUwIiB2aWV3Qm94PSIwIDAgNDAwIDE1MCI+CiAgPHJlY3Qgd2lkdGg9IjQwMCIgaGVpZ2h0PSIxNTAiIHJ4PSI4IiBmaWxsPSIjZjVmNWY1IiBzdHJva2U9IiNjY2MiIHN0cm9va2Utd2lkdGg9IjEiLz4KICA8dGV4dCB4PSIyMCIgeT0iMzUiIGZvbnQtZmFtaWx5PSJtb25vc3BhY2UiIGZvbnQtc2l6ZT0iMTQiIGZpbGw9IiMzMzMiPgogICAgPHRzcGFuIHg9IjIwIiBkeT0iMS4yZW0iIGZpbGw9IiMwMDdiZmYiPi8vIEV4YW1wbGUgZm9yIEphdmEgKHVzaW5nIGEgbGlicmFyeSBsaWtlIE9rSHR0cCBvciBBcGFjaGUgSHR0cENsaWVudCk8L3RzcGFuPgogICAgPHRzcGFuIHg9IjIwIiBkeT0iMS41ZW0iIGZpbGw9IiMwMDdiZmYiPlN0cmluZzwvdHNwYW4+PHRzcGFuIHg9IjgwIiBkeT0iMCIgZmlsbD0iIzMzMyI+IGFwaUtleSA9IDwvdHNwYW4+PHRzcGFuIHg9IjE1MCIgZHk9IjAiIGZpbGw9IiNhMGEwYTAiPiImbHQ7eW91ciBBUEkga2V5Jmd0OyI8L3RzcGFuPjx0c3BhbiB4PSIyNjAiIGR5PSIwIiBmaWxsPSIjMzMzIj47PC90c3Bhbj4KICAgIDx0c3BhbiB4PSIyMCIgZHk9IjEuNWemIiBmaWxsPSIjMDA3YmZmIj5TdHJpbmcgPC90c3Bhbj48dHNwYW4geD0iODAiIGR5PSIwIiBmaWxsPSIjMzMzIj4g...
</details>

#### JavaScript Example
<details><summary>Click to view JavaScript code</summary>
<br>
<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI0MDAiIGhlaWdodD0iMTUwIiB2aWV3Qm94PSIwIDAgNDAwIDE1MCI+CiAgPHJlY3Qgd2lkdGg9IjQwMCIgaGVpZ2h0PSIxNTAiIHJ4PSI4IiBmaWxsPSIjZjVmNWY1IiBzdHJva2U9IiNjY2MiIHN0cm9va2Utd2lkdGg9IjEiLz4KICA8dGV4dCB4PSIyMCIgeT0iMzUiIGZvbnQtZmFtaWx5PSJtb25vc3BhY2UiIGZvbnQtc2l6ZT0iMTQiIGZpbGw9IiMzMzMiPgogICAgPHRzcGFuIHg9IjIwIiBkeT0iMS4yZW0iIGZpbGw9IiMwMDdiZmYiPi8vIEV4YW1wbGUgZm9yIEphdmFTY3JpcHQgKHVzaW5nIEZldGNoIEFQSSk8L3RzcGFuPgogICAgPHRzcGFuIHg9IjIwIiBkeT0iMS41ZW0iIGZpbGw9IiMwMDdiZmYiPmNvbnN0PC90c3Bhbj48dHNwYW4geD0iODAiIGR5PSIwIiBmaWxsPSIjMzMzIj4gYXBpS2V5ID0gPC90c3Bhbj48dHNwYW4geD0iMTYwIiBkeT0iMCIgZmlsbD0iI2EwYTBhMCI+IiZsdDt5b3VyIEFQSSBrZXkmZ3Q7Ijx0c3BhbiB4PSIyNzAiIGR5PSIwIiBmaWxsPSIjMzMzIj47PC90c3Bhbj4KICAgIDx0c3BhbiB4PSIyMCIgZHk9IjEuNWVtIiBmaWxsPSIjMDA3YmZmIj5jb25zdDwvdHNwYW4+PHRzcGFuIHg9IjgwIiBkeT0iMCIgZmlsbD0iIzMzMyI+IHVybCA9IDwvdHNwYW4+PHRzcGFuIHg9IjE0MCIgZHk9IjAiIGZpbGw9IiNhMGEwYTAiPiJodHRwczovL2F1LXN5ZC5tbC5jbG91ZC5pYm0uY29tL21sL3Y0L2RlcGxveW1lbnRzLzYlZT...
</details>

#### Scala Example
<details><summary>Click to view Scala code</summary>
<br>
<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI0MDAiIGhlaWdodD0iMTUwIiB2aWV3Qm94PSIwIDAgNDAwIDE1MCI+CiAgPHJlY3Qgd2lkdGg9IjQwMCIgaGVpZ2h0PSIxNTAiIHJ4PSI4IiBmaWxsPSIjZjVmNWY1IiBzdHJva2U9IiNjY2MiIHN0cm9va2Utd2lkdGg9IjEiLz4KICA8dGV4dCB4PSIyMCIgeT0iMzUiIGZvbnQtZmFtaWx5PSJtb25vc3BhY2UiIGZvbnQtc2l6ZT0iMTQiIGZpbGw9IiMzMzMiPgogICAgPHRzcGFuIHg9IjIwIiBkeT0iMS4yZW0iIGZpbGw9IiMwMDdiZmYiPi8vIEV4YW1wbGUgZm9yIFNjYWxhICh1c2luZyBhIGxpYnJhcnkgbGlrZSByZXF1ZXN0cy1zY2FsYSk8L3RzcGFuPgogICAgPHRzcGFuIHg9IjIwIiBkeT0iMS41ZW0iIGZpbGw9IiMwMDdiZmYiPndhbDwvdHNwYW4+PHRzcGFuIHg9IjYwIiBkeT0iMCIgZmlsbD0iIzMzMyI+IGFwaUtleSA9IDwvdHNwYW4+PHRzcGFuIHg9IjE0MCIgZHk9IjAiIGZpbGw9IiNhMGEwYTAiPiImbHQ7eW91ciBBUEkga2V5Jmd0OyI8L3RzcGFuPgogICAgPHRzcGFuIHg9IjIwIiBkeT0iMS41ZW0iIGZpbGw9IiMwMDdiZmYiPndhbDwvdHNwYW4+PHRzcGFuIHg9IjYwIiBkeT0iMCIgZmlsbD0iIzMzMyI+IHVybCA9IDwvdHNwYW4+PHRzcGFuIHg9IjEyMCIgZHk9IjAiIGZpbGw9IiNhMGEwYTAiPiJodHRwczovL2F1LXN5ZC5tbC5jbG91ZC5pYm0uY29tL21sL3Y0L2RlcGxveW1lbnRzLzYlZT...
</details>

***

### **For your Professional Resume**

**AI-Powered Crop Recommendation System (Fasal Saarthi)** | GitHub: [Link to your GitHub Repo]
* Developed and deployed an **AI-powered crop recommendation system** using **IBM Watsonx.ai Studio** and **AutoAI** to provide data-driven insights to farmers.
* **Engineered an automated machine learning pipeline** that analyzes key soil and environmental parameters (N, P, K, temperature, pH, humidity, rainfall) to generate optimal crop suggestions.
* **Utilized a comprehensive ICFA dataset** to train a high-confidence predictive model, showcasing expertise in data analysis and model development for agricultural applications.
* Designed a system to be API-accessible, providing client code snippets in **Python, Java, JavaScript, and Scala** to demonstrate seamless integration and scalability.

***

### **GitHub Repository Description (for the "About" section):**

**Fasal Saarthi: Kushal Kisan is an AI-powered crop recommendation system built with IBM Watsonx.ai Studio & AutoAI. It analyzes soil and environmental data to provide optimal crop suggestions, empowering farmers with data-driven insights.**
