# To run the Database docker
1. Navigate to the docker\database folder and execute:
    docker build -t <IMAGE_NAME> .

2. To manage the volume (to persist the data):
    docker volume create <VOLUME_NAME>

3. Run the image:
    docker run -d -p 5432:5432 -v <VOLUME_NAME>:<DATA_PATH_IN_YOUR_CONTAINER>(Default Postgres: /var/lib/postgresql/data) --name <CONTAINER_NAME> <IMAGE_NAME>
    PS:
        -d to run the container in background mode
        -p 5432:5432 to map the container's port with your pc .
        -v map the volume created and your folder path container to be saved

4. To test database:
    docker exec -it <CONTAINER_NAME> psql -U postgresql -d ecommerce
    Or
    Use a UI Tool like DBeaver, pgAdmin, HeidiSQL, etc

Helpful:
    To list your docker images:
        ```docker
        docker images
        ```
    To delete a docker image:
        ```docker
        docker rmi <IMAGE_NAME> or <IMAGE_ID>
        ```
    To see the running containers:
        ```docker
        docker ps -a
        ```