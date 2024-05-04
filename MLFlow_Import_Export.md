
We can use MLFlow import export library to import export the databricks models.

# 1. Create databricks Personal Access Token
  User -> Developer -> Access Token -> Manage -> Generate New token
  Once the token is generated, copy and save it somewhere as we won't be able to see this later.

** Source Databricks Workspace **
# 1. Configure Databricks CLI
  Once the token is generated, we need to configure teh Databricks CLI.
  1. Start a cluster in Databricks
  2. Go to Web Terminal 
  3. Type `databricks configure` and hit enter
  4. Enter the host Name : https://XXXX.azuredatabricks.net
  5. Enter the databricks user name : XXXX
  6. Enter the password : paste the token generated from above steps

# 2. Export the model
  %sh
  MLFLOW_TRACKING_URI='databricks://default'
  DATABRICKS_HOST=https://XXXX.azuredatabricks.net
  DATABRICKS_TOKEN=aste the token generated from above steps
  export-experiment \
  -- experiment experiment_id
  -- output-dir /dbfs/FileStore/models/filename

# Download the created tar experiments using below url
  https://XXXX.azuredatabricks.net/files/models/filename.tar
