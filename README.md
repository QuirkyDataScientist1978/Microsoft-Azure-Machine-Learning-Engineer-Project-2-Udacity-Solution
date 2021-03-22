# Microsoft-Azure-Machine-Learning-Engineer-Project-2-Udacity-Solution
Microsoft Azure Machine Learning Engineer Project 2 Udacity Solution. Repository for Udacity Solution. 

## Overview
This project is part of the Udacity Microsoft Azure Machine Learning Engineer Nanodegree Program. During this project we performed an AutoML run on the Bank Marketing Dataset, deployed the best model obtained from the AutoML as a RESTful API Webservice, consumed endpoints to interact with the deployed model in Microsoft Azure Machine Learning Studio and lastly performed pipeline automation to improve machine learning operations.

## Key Steps
**1. Authentication:**
This steps plays an important role in maintaining an uninterrupted flow of operations. Human intervention slows down the process - therefore authentication along with automation is considered an ideal scenario. A Service Principal is one of hte examples of authentication where the user role is defined with user specific permissions.

**2. Automated Machine Learning Experiment to Determine the Best Model:**
We create an AutoML experiment when we first login to the AzureML portal and create a new compute instance for the new experiment. The virtual machine size chosen for the compute cluster is the Standard_DS12_V2 with one node as the minimum number of nodes. The experiment can take between 20 minutes and up to an hour to run with a concurrency of 5. This project actually timed out on me after 5 hours, so I had to run it a second time which means some of the screen prints are from previous runs. As you can see it became quite cumbersome. You really need about 8 hours of Virtual Machine time to complete this project. 

**3. Deploy the Best Model:**
The deployment of a model is the delivery of the best trained model into production so that i can be consumed by others. The best model obtained in the AutoML run is the VotingEnsemble with the highest accuracy of 0.94607. Deploying the model we configured the deployment settings by enabling authentication and using Azure Container Instance (ACI) as it quickly deploys compute instances to deploy models. It is also very simple to utilize. 

**4. Enable Logging:**
Enabling logging is a crucial step in the process vis a vis Enabling Application Insights. Application insights is a tool that helps in detecting anomalies and visualizing performance. It can be enabled before or after the deployment and can be modified with the SDK. In this project, we enable application insights after deploying by adding specific commands to the python SDK. The modified python script displaying logs. 

**5. Swagger Documentation:**
Swagger is a great tool that helps us build, document and consume RESTful API webservices deployed in Azure Machine Learning Studio. It further explains what types of HTTP requests an API can consume, in this case like Post, Get and Update. A swagger.json is provided in the endpoints section of Azure that is used to create a website. This localhost website documents the HTTP endpoint for a deployed model. After running the swagger.sh and serve.py scripts, the webpage idsplays the contents of the API for the best model along with different HTTP requests supported. 

**6. Consume Model endpoints:**
Lastly, the deployed service is consumed via an HTTP API. We initiate an inpute request, in this case via an HTTP Post request method to submit data. The HTTP GET request is another request method to retrieve information from a web server. This creates a bi-directional flow of allowed information in Azure. In order to consume deployed services, we modify the URI and key to match the primary key for our service and RESTful URI is generated after deployment. The execution of the endpoint.py script after modification gives the output. 

### Project 2 Architecture<img src="/images/Slide1.PNG">
### Authenticate, Update, Install Azure CLI<img src="/images/Slide2.PNG">
### Azure CLI Login<img src="/images/Slide3.PNG">
### Azure CLI Login Picture 2<img src="/images/Slide4.PNG">
### Azure Principal Service Already Setup<img src="/images/Slide5.PNG">
### Azure CLI Login<img src="/images/Slide6.PNG">
### Azure CLI Login Picture 2<img src="/images/Slide7.PNG">
### Azure Bank Marketing Dataset Final Deployment<img src="/images/Slide8.PNG">
### Azure Bank Marketing Dataset Final Deployment Picture 2<img src="/images/Slide9.PNG">
### Insights Client & GET API Test with 200 Message - Success<img src="/images/Slide10.PNG">
### Azure endpoint.py Script Run<img src="/images/Slide11.PNG">
### Bank Marketing Dataset Final Deployment with Authentication Keys<img src="/images/Slide12.PNG">
### Azure Datastore Service Principal<img src="/images/Slide14.PNG">
### Bank Marketing Dataset<img src="/images/Slide15.PNG">
### Bank Marketing Dataset Picture 2<img src="/images/Slide16.PNG">
### Azure Run Complete<img src="/images/Slide17.PNG">
### Azure Run<img src="/images/Slide18.PNG">
### Azure Pipeline Overview<img src="/images/Slide19.PNG">
### Azure Best Model<img src="/images/Slide20.PNG">
### Azure Best Model<img src="/images/Slide21.PNG">
### Azure Pipeline Endpoints<img src="/images/Slide22.PNG">
### Azure Bank Marketing Pipeline<img src="/images/Slide23.PNG">
### Azure Best Model<img src="/images/Slide24.PNG">
### Azure Published Pipeline Overview<img src="/images/Slide25.PNG">
### Azure Model Registration<img src="/images/Slide26.PNG">
### Azure Model Deployment<img src="/images/Slide27.PNG">
### Azure Machine Learning Insights<img src="/images/Slide28.PNG">
### Pipeline Completion & PipelineWidget<img src="/images/Slide29.PNG">
### Best Model<img src="/images/Slide30.PNG">
### Azure Model Deployment<img src="/images/Slide31.PNG">
### Running Azure Swagger CLI<img src="/images/Slide32.PNG">
### Azure Swagger Localhost API Call<img src="/images/Slide33.PNG">
### Azure HTTP API Call<img src="/images/Slide34.PNG">
### Create Azure ML Experiment<img src="/images/Slide35.PNG">
### Bank Marketing DataFrame Statistics<img src="/images/Slide36.PNG">
### Azure Machine Learning Execution Summary<img src="/images/Slide37.PNG">
### Azure Machine Learning Pipeline Execution Summary<img src="/images/Slide38.PNG">
### Azure Machine Learning Finished Pipeline Summary<img src="/images/Slide39.PNG">
### Pipeline Best Model<img src="/images/Slide40.PNG">
### Pipeline Best Model Steps<img src="/images/Slide41.PNG">
### Publish and Run from REST endpoint<img src="/images/Slide42.PNG">
### Azure Pipeline Run<img src="/images/Slide43.PNG">
### Azure Pipeline API endpoints for swagger.json<img src="/images/Slide44.PNG">
### Azure Pipeline JSON Payload<img src="/images/Slide45.PNG">
### Azure Pipeline Swagger Run localhost:9000<img src="/images/Slide46.PNG">

## Future Improvements
Benchmarking can be done using Apache Benchmark command-line tool to keep the performance of the model in check and above a standard level. It is used to determine the response time in seconds for the model that is deployed. Additionally, you could try different models to get the best possible one. This couldn't be done due to the costs incurred within the Virtual Machine. If we reduced the duration of the experiment or increased the number of processes running in parallel then the experiment will be fast and time can be save - however resource costs may increase. The use of the Kubernetes service can be helpful in case we add more data to the existing dataset. This was a very challenging project and am happy it's finished. This project took approximately 9 hours to complete. 

## Video Link

### [Video Link](https://www.dropbox.com/s/upoew9usg5a2idj/Recording%20%238.mp4?dl=0)
### [Video Link 2: Pipeline-Endpoint](https://www.dropbox.com/s/fzht649bdokbl2k/Recording%20%2310.mp4?dl=0)
