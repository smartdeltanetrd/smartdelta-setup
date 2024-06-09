# SmartDelta  DIA4M Setup Guide

## Prerequisites
- Install Docker and Docker Compose.

## Setup Instructions

1. Create a folder called `SmartDelta`:
    ```sh
    mkdir SmartDelta
    ```

2. Navigate to the `SmartDelta` folder:
    ```sh
    cd SmartDelta
    ```

3. Clone the repositories: 
    ```sh
    git clone -b dev-eren https://github.com/smartdeltanetrd/smartdelta-frontend.git
    git clone -b dev-eren https://github.com/smartdeltanetrd/smartdelta-backend-ts.git
    ```
    Note: For each repo create a new branch(dev-yourName) and switch to your new branch for development.

4. Download the `docker-compose.yml` file from the setup guide repository and move it to the root of `SmartDelta`.

5. Run the following command in the root of `SmartDelta` folder:
    ```sh
    docker compose up
    ```

6. Wait a few minutes for the containers to be created and started.
7.  If you get an error related the mongo_db file permission run  `sudo chmod -R 755 /mongo_db` on MACOS or Lınux. If you use Windows, then run `icacls C:\mongo_db /grant %username%:F /T
icacls C:\mongo_db /grant Users:(RX) /T`
 
8. Verify the setup:
    - Navigate to `http://localhost:5000`. You should see the following JSON response:
      ```json
      {"message":"Hello World"}
      ```
      This indicates that the Node.js API is running without issues.
      
    - Navigate to `http://localhost:3000` to check if the frontend is running without issues.

9. In the frontend app:
    - Click on the file upload menu item and upload one of the CSV files in the repository.
    - After uploading the file, you will be navigated to the mapping visualizer.
    - Go back to the file upload page to see the uploaded file list in the manage file part.
    - If you see the uploaded file as a list item, it means the frontend, MongoDB, and Node.js API are running without issues.

## Logs
- To see the logs of the frontend app, open a terminal under the root of `smartdelta-frontend` and run:
    ```sh
    docker logs -f smartdelta-frontend-1
    ```

- To see the live changes of the Node.js API logs, open a terminal under the root of `smartdelta-backend` and run:
    ```sh
    docker logs -f smartdelta-api-1
    ```

## Data Science Flask API Setup

1. Under the root of `SmartDelta` folder, clone the `smartdelta-ml-backend` repository:
    ```sh
    git clone https://github.com/smartdeltanetrd/smartdelta-ml-backend.git
    ```

2. Follow the guideline on this [link](https://github.com/smartdeltanetrd/smartdelta-ml-backend/blob/master/README.md).


## Directory Structure
After completing the setup steps, your `SmartDelta` directory should look like this:

![Ekran Görüntüsü - 2024-05-31 12-02-54](https://github.com/erentrk01/DIA4M-SETUP/assets/68688967/820eaad6-7db5-4455-8bdf-a29844422543)


## How to stop containers
Under the root of SmartDelta folder,
    docker compose down
  
## How to restart containers
   docker compose up

## How to list running containers 
   docker ps




