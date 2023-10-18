# dlt_dbt_cloud
Repository with demos of using DLT and DBT Cloud

## Installation

`pip install dlt[bigquery]`

## Init the pipeline 

`dlt init pokemon bigquery`

## Update pipeline script

Add the following code into your pipeline script (`pipelines/pokemon_pipeline.py`):

```python
from dlt.helpers.dbt_cloud import run_dbt_cloud_job

run_info = run_dbt_cloud_job()
print(f"Job run status: {run_info['status_humanized']}")
```

## Credentials

```toml
[dbt_cloud]
api_token = "set me up!" # required for authentication
account_id = "set me up!" # required for both helpers function
job_id = "set me up!" # optional only for run_dbt_cloud_job function (you can pass this explicitly as an argument to the function)
```

More information about dbt cloud helpers in [DBT Cloud Client and Helper Functions](https://dlthub.com/docs/dlt-ecosystem/transformations/dbt/dbt_cloud).