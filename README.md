# Data Monitoring and Analysis Platform

This project sets up a complete data monitoring and analysis environment using Docker containers. The platform consists of three main components:

## Components

### 1. Grafana (Port: 3000)
- Web-based visualization and monitoring platform
- Accessible at `http://localhost:3000`
- Persistent data storage in `./grafana_data`

### 2. InfluxDB (Port: 8086)
- Time-series database for storing metrics and events
- Accessible at `http://localhost:8086`
- Initial setup credentials:
  - Username: admin
  - Password: adminpass
  - Organization: demoorg
  - Bucket: adatok
  - Admin Token: admintoken
- Persistent data storage in `./influxdb_data`

### 3. Jupyter Notebooks (Port: 8888)
- Interactive development environment for data analysis
- Accessible at `http://localhost:8888`
- Notebooks stored in `./jupyter_notebooks`

## Getting Started

1. Ensure you have Docker and Docker Compose installed on your system
2. Clone this repository
3. Run the following command to start all services:
   ```bash
   docker-compose up -d
   ```
4. Access the services through their respective ports:
   - Grafana: http://localhost:3000
   - InfluxDB: http://localhost:8086
   - Jupyter: http://localhost:8888

## Network Configuration

The project uses two Docker networks:
- `web`: For external-facing services
- `internal`: For internal service communication

## Data Persistence

All data is persisted in the following directories:
- `./grafana_data`: Grafana configurations and dashboards
- `./influxdb_data`: InfluxDB time-series data
- `./jupyter_notebooks`: Jupyter notebooks and data files

## Security Note

The default credentials provided in this setup are for demonstration purposes only. In a production environment, please:
1. Change all default passwords
2. Use secure tokens
3. Implement proper authentication mechanisms
4. Consider using environment variables for sensitive data