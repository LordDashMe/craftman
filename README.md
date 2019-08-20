# Craftman

Automation Script for Docker Compose Service.

## Requirements

- Docker version 17.x.x or higher.

- Python 2.7.x or higher.

## Folder Structure

```bash
.
├── boilerplate
│   ├── .sample-docker-compose
│   ├── .sample-env
│   ├── .sample-README
├── service
│   ├── category
│       ├── service
│           ├── .env
│           ├── docker-compose.yml
│           ├── README.md
├── storage
│   ├── service-network
├── tmp
│   ├── .gitignore
├── README.md
├── craftman
```

## Usage

- To check the script available functions, use the command ```./craftman help```.

- To check the options of a function, use the command ```./craftman [function...] --help```.

### Setup Network Development

- To setup the development docker network provided by craftman automation script, use the command below:

  ```text
  ./craftman network
  ```

#### Network Specification

- When using the provided development docker network setup, the specification or details are listed below:

  - Network Class: A

  - Subnet: 255.0.0.0/8

  - IP Address: 116.0.0.0/116.255.255.254

  - Port: 16000/65535

### Setup Service

- To setup a service/project, use the function ```./craftman service```.

  ```text
  ./craftman service --ip=116.0.0.2 --port=16002 --service=mysql-5.6 --category=common
  ```

### Setup Environment File

- To setup an environment or ```.env``` file in the service/project, use the function ```./craftman environment```.

  ```text
  ./craftman environment --path=service/common/mysql-5.6/ --host=my-machine-name
  ```

  - By default craftman script will not include ```.env``` file when used to generate service/project.

  - For "flexibility" purpose, the ```.env``` file should be manually create or apply by the crafter.

  - The generated ```docker-compose.yml``` file requires the ```LOCAL_MACHINE_USERNAME``` ENV variable, thus requires to provide a ```.env``` in the same directory or level of the said file.

  - The ```.env``` file will automatically read by the docker compose command as long as they are the same directory or level with ```docker-compose.yml```.

  - If you want to deeply understand how environment work with the docker compose you can check this reference documentation: [Environment variable in Compose | Docker Documentation](https://docs.docker.com/compose/environment-variables/)

## Reference Tools

- [Subnet Calculator](https://www.calculator.net/ip-subnet-calculator.html?cclass=any&csubnet=8&cip=116.0.0.0&ctype=ipv4&printit=0&x=49&y=21)

## License

This package is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
