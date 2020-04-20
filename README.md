# Setup
You'll need to have a `dwh.cfg` config file in the root of this directory. It needs to contain these values:
```
[AWS]
KEY=YOUR_KEY
SECRET=YOUR_SECRET

[DWH] 
DWH_CLUSTER_TYPE=multi-node
DWH_NUM_NODES=4
DWH_NODE_TYPE=dc2.large

DWH_IAM_ROLE_NAME=dwhRole
DWH_CLUSTER_IDENTIFIER=dwhCluster
DWH_DB=dwh
DWH_DB_USER=dwhuser
DWH_DB_PASSWORD=Passw0rd
DWH_PORT=5439

DWH_ROLE_ARN=YOUR_DWH_ROLE_ARN
DWH_ENDPOINT=YOUR_DWH_ENDPOINT

[TINYBIRD]
TOKEN=YOUR_TOKEN
```


# Instalation
Do `export LDFLAGS="-L/usr/local/opt/openssl/lib" export CPPFLAGS="-I/usr/local/opt/openssl/include"` or psycopg2 will fail to install
Then, do `pipenv install`

# Launching Redshift cluster
Follow along the code in `Launch and kill Redshift cluster.ipynb` to create the Redshift cluster, IAM Roles and attach the necessary policies to create and then delete the cluster

# Run
The main parts of the code are in the `Redshift - Tinybird` notebook, to load data from S3 to Redshift, download it to disk and then load it to Tinybird from disk