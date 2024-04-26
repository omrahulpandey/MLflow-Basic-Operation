# MLflow-Basic-Operation



## For Dagshub:
'''bash
MLFLOW_TRACKING_URI=https://dagshub.com/omrahulpandey/MLflow-Basic-Operation.mlflow \
MLFLOW_TRACKING_USERNAME=omrahulpandey \
MLFLOW_TRACKING_PASSWORD=bd2c625b6e5ecda08a3c8121476affccf461f306 \
python script.py


'''bash
export MLFLOW_TRACKING_URI=https://dagshub.com/omrahulpandey/MLflow-Basic-Operation.mlflow

export MLFLOW_TRACKING_USERNAME=omrahulpandey

export MLFLOW_TRACKING_PASSWORD=bd2c625b6e5ecda08a3c8121476affccf461f306


'''



# MLflow on AWS

## MLflow on AWS Setup:

1. Login to AWS Console.
2. Create IAM user with AdministratorAccess.
3. Export the credentials in your AWS CLI by running "aws configure".
4. Create a s3 bucket.
5. Create EC2 instance (Ubuntu) & add Security groups 5000 port.


Run the following commands on EC2 instance-
'''bash
sudo apt update

sudo apt install python3-pip

sudo pip3 install pipenv

sudo pip3 install virtualenv

mkdir mlflow

cd mlflow

pipenv install mlflow

pipenv install awscli

pipenv install boto3

pipenv shell


## Then set aws credentials
aws configure


#Finally
mlflow server -h 0.0.0.0 --default-artifact-root s3://mlflow-bukt01


#open Public IPv4 DNS to the port 5000


#set uri in your local terminal and in your code.
export MLFLOW_TRACKING_URI = http://ec2-13-127-216-228.ap-south-1.compute.amazonaws.com:5000/
'''