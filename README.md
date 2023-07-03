# Training and deploying an ML model in Azure

This is the final project for course 2, "Machine Learning Operations," from Udacity's Machine Learning Engineer with Microsoft Azure nanodegree.

In this project we go through the full ML pipeline, from getting and loading the data to deploying and consuming an ML model.


## Architectural Diagram

![Architectural diagram](images/architectural_diagram.png)

1. Data. Upload csv file and create a data asset in Azure ML
2. Compute. Create both a compute cluster, to train the model, and a compute instance, to run notebooks.
3. AutoML. We used AutoML to automatically train several models and pick the best one.
4. Deploy.
   - Using Swagger, we get a UI but run into problems
   - Using the `endpoint.py` script, we can consume the model ang receive JSON output
5. Pipeline. We create and publish a pipeline using a Jupyter notebook.

## Key Steps

We created the following resources, both on Azure and locally on Udacity's VM.

| Type               | Name                     | Observations    |
|--------------------|--------------------------|-----------------|
| Compute cluster    | edu-pro2-compute-cluster | Standard_DS3_v2 |
| Compute instance   | edu-pro2-compute-inst    | Standard_DS3_v2 |
| Tabular data asset | edu-pro2-data            |                 |
| Auto ML Job        | edu-pro2-exp             |                 |
| Deployed model     | edu-pro2-deploy          |                 |
| Python venv        | edu-pro2-venv            | Local (on VM)   |


- Create a data asset in Azure

![Dataset](images/Screenshot_20230703_212312_dataset.png)

- Auto ML job is complete

![Auto ML job complete](images/Screenshot_20230703_214041_auto_ml_job_completed.png)

- Best model

![Best model](images/Screenshot_20230703_214134_best_model.png)

- Application insights enabled

![App insights enabled](images/Screenshot_20230703_221014_application_insights_enabled.png)

- Logs provided by `logs.py` script

![Logs](images/Screenshot_20230703_220916_logs.png)

- Deployment in Swagger UI

![Swagger UI](images/Screenshot_20230703_221751_swagger_edu_pro2_deploy.png)

- Failed to fetch error

![Error](images/Screenshot_20230703_222054_swagger_http_failed_to_fetch.png)

- Results from `endpoint.py` script

![Results](images/Screenshot_20230703_224236_endpoint_results.png)

- Pipeline jobs

![Pipeline jobs](images/Screenshot_20230703_233909_pipeline_jobs.png)

- Pipeline endpoints

![Pipeline endpoints](images/Screenshot_20230703_234021_pipeline_endpoints.png)

- Published pipeline overview

![Published pipeline overview](images/Screenshot_20230703_234149_dataset_active_endpoint.png)

- `RunDetails` widget in notebook

![RunDetails](images/Screenshot_20230703_234448_notebook_run_details_start.png)


## Screen Recording

Screencast: https://youtu.be/o3wwtlRSz_c


## Standout Suggestions

Instead of relying on the `endpoint.py` file on the `starter_files` folder, which didn't work,
I adapted the script from the "Consume" tab of the deployed model.

Swagger UI wasn't able to provide output from the model, although I tried both HTTP and HTTPS modes.
