# Dependency Analysis

This document provides a summary of the dependencies for the Data-Beans demo project.

## System-Level Dependencies

These dependencies are required on the machine used to deploy the project. They are typically installed using a package manager like `apt` or `yum`.

- **git:** For cloning the repository.
- **curl:** For making HTTP requests.
- **jq:** A command-line JSON processor.
- **gcloud (Google Cloud CLI):** For interacting with Google Cloud Platform.
  - **gcloud beta:** Some commands may require the beta components of the gcloud CLI.
- **terraform:** For managing the infrastructure as code.

## Python Dependencies

The project uses Python for both its cloud functions and Jupyter notebooks.

### Cloud Function Dependencies

The dependencies for the cloud function are defined in `qwiklabs/terraform-modules/colab-deployment/cloud-function/requirements.txt`:

- `functions-framework==3.*`
- `google-cloud-dataform==0.5.5`

### Jupyter Notebook Dependencies

The Jupyter notebooks in this project have the following dependencies. These are typically installed via `pip` within the notebook environment.

- **pandas:** For data manipulation and analysis.
- **bigframes:** A Python package that provides a pandas-like API for BigQuery.
- **google-cloud-bigquery:** The Google Cloud client library for BigQuery.
- **google-cloud-vision:** The Google Cloud client library for Vision AI.
- **google-cloud-aiplatform:** The Google Cloud client library for Vertex AI.
- **google-cloud-texttospeech:** The Google Cloud client library for Text-to-Speech.

## Infrastructure Dependencies

The project's infrastructure is managed by Terraform. The Terraform configuration files (`.tf`) are located in the `terraform` and `terraform-modules` directories. These files define all the necessary Google Cloud Platform resources, including but not limited to:

- Google Cloud Project
- BigQuery datasets and tables
- Cloud Functions
- Vertex AI resources (Notebooks, Models, etc.)
- IAM policies and service accounts
- Cloud Storage buckets

For a complete list of infrastructure dependencies, please refer to the Terraform files in the repository.

## External API Dependencies

The project has a dependency on an external API:

- **serpapi.com:** An API key from serpapi.com is required to run the `Event-Populate-Table` notebook, which fetches event data.
