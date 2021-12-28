#Docker Image for OracleDB
## Preliminary steps:

Install docker:
</br>
Linux - https://docs.docker.com/engine/install/
</br>
Windows - https://docs.docker.com/desktop/windows/install/


## Steps:
1. Get oracle project
```
git clone https://github.com/oracle/docker-images.git
cd docker-images/OracleDatabase/SingleInstance/dockerfiles
```

2. Specify the version and edition of the database to build
```
./buildContainerImage.sh -v 21.3.0 -x
```

3. Start the container
```
docker run --name myxedb \
    -d \
    -p 51521:1521 \
    -p 55500:5500 \
    -e ORACLE_PWD=password \
    -e ORACLE_CHARACTERSET=AL32UTF8 \
    oracle/database:21.3.0-xe
```