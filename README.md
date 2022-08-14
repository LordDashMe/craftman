# Craftman

An automation script that manage your dockerized local development setup.

## The Purpose

If you want to dockerize your local development and manage it in an easier way, this will be your friend to help or guide you to do that in a simple way.

## Requirement(s)

- Docker version 17.x.x or higher.

- Docker Compose version 1.17.x or higher.

- Python 2.7.x or higher.

## Install

- Download the latest release here: [Latest Release of Craftman](https://github.com/LordDashMe/craftman/archive/0.2.0.zip)

- Check other releases here: [Releases of Craftman](https://github.com/LordDashMe/craftman/releases)

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
├── .gitignore
├── LICENSE
├── README.md
└── craftman
```

## Usage

- To check the script available modules, use the command ```./craftman help```.

- To check the options of a modules, use the command ```./craftman [module...] --help```.

### Setup Network Development

- To setup the development docker network provided by craftman automation script, use the command below:

  ```text
  ./craftman network
  ```

#### Network Specification

- When using the provided development docker network setup, the specification or details are listed below:
  
  - Docker Network Name: development-network

  - Network Class: A

  - Subnet: 255.0.0.0/8

  - IP Address: 116.0.0.0/116.255.255.254

  - Port: 16000/65535

### Setup Service

- To setup a service/project, use the module ```./craftman service```.

  ```text
  ./craftman service --ip=116.0.0.2 --port=16002 --service=mysql-5.6 --category=common
  ```

### Setup Environment File

- To setup an environment or ```.env``` file in the service/project, use the module ```./craftman environment```.

  ```text
  ./craftman environment --path=service/common/mysql-5.6/ --host=my-machine-name
  ```

  - By default craftman script will not include ```.env``` file when used to generate service/project.

  - For "flexibility" purpose, the ```.env``` file should be manually create or apply by the crafter.

  - The generated ```docker-compose.yml``` file requires the ```LOCAL_MACHINE_USERNAME``` ENV variable, thus requires to provide a ```.env``` in the same directory or level of the said file.

  - The ```.env``` file will automatically read by the docker compose command as long as they are the same directory or level with ```docker-compose.yml```.

  - If you want to deeply understand how environment work with the docker compose you can check this reference documentation: [Environment variable in Compose | Docker Documentation](https://docs.docker.com/compose/environment-variables/)

### Check Storage

- To check the last entry in the storage, use the module ```./craftman storage```.

### Remove Service

- To remove service entry, use the module ```./craftman service-delete --ip=<192.168.x.x> --service=<service-name> --category=<category-name>```

## Reference Tool(s)

- [Subnet Calculator](https://www.calculator.net/ip-subnet-calculator.html?cclass=any&csubnet=8&cip=116.0.0.0&ctype=ipv4&printit=0&x=49&y=21)

## License

This package is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
