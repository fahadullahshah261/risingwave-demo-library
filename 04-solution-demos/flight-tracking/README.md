# Real-time Flight Tracking with RisingWave, Kafka, and Metabase

This directory  provides instructions and resources for building a real-time flight tracking system using RisingWave, Kafka, and Metabase. Follow these steps to set up and run the demo:

## Prerequisites

- Docker and Docker Compose installed on your system.
- PostgreSQL interactive terminal (`psql`) for running SQL queries.

## Getting Started

1. Clone this repository to your local machine:

    ```bash
    git clone https://github.com/risingwavelabs/awesome-stream-processing.git
    ```

2. Navigate to the cloned directory:

    ```bash
   cd risingwavelabs/awesome-stream-processing/04-solution-demos/flight-tracking
    ```

3. Run the Docker Compose file to create the demo environment:

    ```bash
    docker-compose up -d
    ```

    This command will create the RisingWave demo cluster, Kafka cluster, and Metabase. It will also fetch flight data from the Aviationstack API and send it to a Kafka topic for processing.

4. Connect to the RisingWave database using the PostgreSQL interactive terminal:

    ```bash
    psql -h localhost -p 4566 -d dev -U root
    ```

5. Run the SQL queries in `demo.sql` to create a source and different materialized views in RisingWave for real-time analysis.

## Using Metabase

1. Access Metabase in your browser by visiting [http://localhost:3000](http://localhost:3000).

2. Set up Metabase to connect to the RisingWave database as a data source. Use the following connection details:
    - Host: `localhost`
    - Port: `4566`
    - Database Name: `dev`
    - Username: `root`
    - Password: `<your_password>`

3. Create charts and a dashboard in Metabase based on the materialized views in RisingWave. Visualize real-time flight data and generate insightful reports.

## Additional Notes

- Ensure all Docker containers are running before accessing RisingWave, Kafka, and Metabase.
- Refer to [RisingWave documentation](https://docs.risingwave.com/docs/current/intro) for more information about connecting RisingWave with Kafka and Metabase. 
