Setting up the System

This Docker Compose file allows you to easily spin up Zookkeeper, Kafka and Postgres application in Docker containers.

Prerequisites

Python 3.9 or above installed on your machine
Docker Compose installed on your machine
Docker installed on your machine
Steps to Run

Clone this repository.
Navigate to the root containing the Docker Compose file.
Run the following command:
docker-compose up -d
This command will start Zookeeper, Kafka and Postgres containers in detached mode (-d flag). Kafka will be accessible at localhost:9092 and Postgres at localhost:5432.

Additional Configuration

If you need to modify Zookeeper configurations or change the exposed port, you can update the docker-compose.yml file according to your requirements.

Running the App

##### Install the required Python packages using the following command:
pip install -r requirements.txt
##### Creating the required tables on Postgres and generating voter information on Kafka topic:
python main.py
##### Consuming the voter information from Kafka topic, generating voting data and producing data to Kafka topic:
python voting.py
##### Consuming the voting data from Kafka topic, enriching the data from Postgres and producing data to specific topics on Kafka:
python spark-streaming.py
##### Running the Streamlit app:
streamlit run streamlit-app.py
