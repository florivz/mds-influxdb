# InfluxDB vs Oracle Database Performance: IoT Telemetry Data

## Project Goal

Evaluate and compare the performance of InfluxDB 2.7 (a time-series database) with Oracle SQL Database for storing and querying IoT telemetry data. This project is part of the University Module "Modern Database Systems" at TH Cologne.

## Getting Started

1. Create and activate a virtual environment. For example, with `venv`:
   ```bash
   python -m venv .venv
   # Windows
   .venv\\Scripts\\activate
   # macOS/Linux
   source .venv/bin/activate
   ```
2. Install the required libraries from the `requirements.txt` file:
   ```bash
   pip install -r requirements.txt
   ```
3. Create a `.env` file in the project's root directory and add your InfluxDB token. You can use the `.env.example` file as a template (if available) or create a new file with the following content:
   ```dotenv
   INFLUXDB_TOKEN=YOUR_INFLUXDB_TOKEN_HERE
   ```

## Dataset

The dataset consists of environmental sensor telemetry data collected from multiple IoT devices. It contains temperature, humidity, gas, light, and motion readings, each with a timestamp and device ID. The data was sourced from Kaggle: [Environmental Sensor Data](https://www.kaggle.com/datasets/garystafford/environmental-sensor-data-132k). For details on the data structure, see the Kaggle page or the `data/iot_telemetry_data.csv` file in this repository.

| column   | description          | units      |
| -------- | -------------------- | ---------- |
| ts       | timestamp of event   | epoch      |
| device   | unique device name   | string     |
| co       | carbon monoxide      | ppm (%)    |
| humidity | humidity             | percentage |
| light    | light detected?      | boolean    |
| lpg      | liquid petroleum gas | ppm (%)    |
| motion   | motion detected?     | boolean    |
| smoke    | smoke                | ppm (%)    |
| temp     | temperature          | Fahrenheit |

## Methodology

- Import the same IoT telemetry dataset into both InfluxDB 2.7 and Oracle Database.
- Perform typical time-series queries (e.g., aggregations, filtering by time/device, downsampling).
- Measure and compare query performance, data ingestion speed, and storage efficiency.
- Summarize findings and provide recommendations for similar IoT analytics scenarios.

## Tools and Technologies Used

- InfluxDB 2.7
- Oracle SQL Database
- Python (see `requirements.txt`)
- Jupyter Notebook (`influxdb.ipynb`)

---
