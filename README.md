# Data Toolbox

Dockerized environment for prototyping, tracking and saving progress for ML experiments, which provides:
* Jupyter notebook server on `localhost:8888`
* MLFlow tracking server on `localhost:5000`
* Postgresql database for saving experiments

### Setup:
1. Install `docker` and `docker-compose`.
2. Copy this to a shared directory.
3. If running for the first time execute `docker-compose build`, otherwise skip this step.
4. Execute `docker-compose up` from root directory.

### MLFlow usage with Python:
```
import mlflow

mlflow.set_tracking_uri('http://localhost:5000')
mlflow.set_experiment('my_experiment_name')

with mlflow.start_run():
    mlflow.log_param('my_param', 0.0001)
    mlflow.log_metric('my_metric', 123) 
```