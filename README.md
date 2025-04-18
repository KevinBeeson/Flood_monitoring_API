# UK Flood Monitoring Data Analysis

## Overview
This project fetches and analyses flood monitoring data from the UK Environment Agency's API. Users can select a station, filter data for the last 24 hours, and visualise the measurements.

## API source
API Source
This project uses the UK Government's Flood Monitoring API:

- Base API URL: https://environment.data.gov.uk/flood-monitoring/id/stations

## Using Docker

You can run the Hurricane Loss Simulation using a pre-built Docker image available on [Docker Hub](https://hub.docker.com/r/kevinbeeson/flood_monitoring_api), eliminating the need to build it locally.

### 1. Pull the Docker Image if you would like it saved locally or just run the docker command

```bash
docker pull kevinbeeson/flood_monitoring_api:latest
```


### 2. Or Just run using Docker 

If you would like to run it through docker you can 

```bash
docker run -p 8501:8501 --rm kevinbeeson/flood_monitoring_api:latest
```


## Requirements

- Python 3.x
- pandas
- matplotlib
- requests
- streamlit

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/KevinBeeson/Flood_monitoring_API
    cd Flood_monitoring_API
    ```

2. Create a virtual environment (recommended):
    ```bash
    python -m venv Flood_monitoring
    ```

3. Activate the virtual environment:
    - On Linux:
        ```bash
        source Flood_monitoring/bin/activate
        ```
    - On Windows:
        ```bash
        ./Flood_monitoring/scripts/activate
        ```

4. Install the required packages:

    ```bash
    pip install pandas tqdm matplotlib requests streamlit
    ```
    
    Or:
    
    ```bash
    pip install -r requirements.txt
    ```
## Features
- Fetches live flood monitoring station data
- Allows user selection of a station based on parameters like town or river name
- Supports filtering and visualisation of specific measurement types
- Plots the last 24 hours of data using Matplotlib

## Example run

To run the program, use the following command:
```bash
 streamlit run water_level.py 
```
The program will then fetch all the names of the stations, and the user can start narrowing down the database to their wanted water station or just select a water station.


The user can now narrow down these stations using the parameters ['id_name', 'town', 'catchmentName', 'riverName', 'label']; the program will narrow down this selection. Note the input won't be case sensitive.



This process repeats until only a single station is available or the user selects restart. If the user selects restart, all original stations will be available for them to choose from again.


You can select which numbers to plot. Multiple measurements can be plotted on one measurement.
