# elk

This repository demonstrates a "Hello-World" setup for the ELK (Elasticsearch, Logstash, Kibana) stack using Docker. It includes a simple pipeline to process a sample log file and visualize it in Kibana.

## Directory Structure
```
elk/
├── docker-compose.yml       # Docker Compose file to spin up Elasticsearch, Logstash, and Kibana
├── logstash/                # Logstash-related configurations
│   ├── pipeline.conf        # Logstash pipeline to process logs
│   └── logs/                # Folder for sample log files
│       └── example.log      # A sample log file for demonstration
└── README.md                # Project documentation
```

## Prerequisites

1. **Docker** and **Docker Compose** installed on your machine.
2. Basic familiarity with Docker and the ELK stack.

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/rexlim820220/elk.git
cd elk
```

### 2. Launch the ELK Stack
Run the following command to start the services:
```bash
docker-compose up
```

### 3. Access the Services
- **Kibana**: Visit [http://localhost:5601](http://localhost:5601) in your browser.
- **Elasticsearch**: Access it at [http://localhost:9200](http://localhost:9200).

### 4. View Logs in Kibana
1. Navigate to the Kibana homepage.
2. Set up an index pattern for `logs` under "Stack Management" → "Index Patterns".
3. Explore the parsed logs in the "Discover" tab.

## Logstash Pipeline Overview
The `pipeline.conf` processes a sample log file (`example.log`) and sends structured data to Elasticsearch with the following fields:
- `timestamp`: Log time.
- `level`: Log severity (INFO, ERROR, etc.).
- `message`: Log message.

## Stopping the Stack
To stop the ELK stack, press `CTRL+C` or run:
```bash
docker-compose down
```

## License
This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
