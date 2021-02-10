# Wine Quality Machine Learning Example

ML example with logging experiments and artifacts in remote MLflow server. Noting MLflow client (in Python) and server need to share the same (NFS) filesystem for artifacts storing.

```bash
# Custom Python Environment
python -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install pandas sklearn jupyter mlflow

# MLflow
mlflow server --backend-store-uri sqlite:///database.sqlite --default-artifact-root $(pwd)/mlruns &

# Simulate remote MLflow
export MLFLOW_TRACKING_URI=http://127.0.0.1:5000

# Jupyter
jupyter notebook &
```
