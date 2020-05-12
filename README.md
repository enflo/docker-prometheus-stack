# DOCKER PROMETHEUS STACK

## REQUIREMENTS
 - DOCKER
 - DOCKER COMPOSE

## FIRST START

1- Fork the project
2- Adjust all settings, changes are marked with ##TODO
    - docker-compose.yml
    - init-letsencrypt.sh
    - prometheus/prometheus.yml
        - nginx/grafana.conf
    - nginx/prometheus.conf
    - alertmanger/config.yml
3- Generate .htpasswd into nginx/.htpasswd
    ```bash
        htpasswd -c nginx/.htpasswd USERNAME
    ```
4- Generate certs  (more info https://medium.com/@pentacent/nginx-and-lets-encrypt-with-docker-in-less-than-5-minutes-b4b8a60d3a71)
5- Start all containers
    ```bash
        docker-compose up -d
    ```

## MANAGE

If you edit the configuration once the cluster is started, you have to restart the containers.
    ```bash
        docker-compose down  CONTAINER_NAME &&  docker-compose up -d CONTAINER_NAME
    ```

## TODO
- [ ] Automate settings enviroment
- [ ] Add Exporters
