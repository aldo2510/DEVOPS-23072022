# Lab06

### Tag images

* Limpiar (opcional)
    ```bash
    docker system prune -a
    ```

*  Generar website:1.0.0
    ```bash
    docker build -t website -f ./1.0/Dockerfile ./1.0/
    docker build -t website .
    docker build -t website:latest .
    docker build -t website:1.0.0 .

    docker tag website:latest website:1.0.0
    docker tag website:latest aldot25/website:1.0.0

    docker build -t website -f ./2.0/Dockerfile ./2.0/
    docker build -t modventas:2.0.0 .
    docker tag modventas:2.0.0 aldot25/modventas:2.0.0
    docker tag modventas:2.0.0 aldot25/modventas:latest

    docker tag website:latest website:2.0.0
    docker tag website:latest aldot25/website:2.0.0
    ```

* Docker hub login
    ```bash
    docker login docker.io
    <<user>>/<<repository name>>:<<tag>>
    ```

* Push Azure Registry
    ```bash
    docker login galaxytraining01.azurecr.io -u galaxytraining01
    <<url repository>>/<<repository name>>:<<tag>>

    docker tag website:latest galaxytraining01.azurecr.io/website:1.0.0
    docker tag website:latest galaxytraining01.azurecr.io/website:2.0.0

    docker tag modventas:2.0.0 galaxytraining01.azurecr.io/modventas:aldot25
    docker push galaxytraining01.azurecr.io/modventas:aldot25

    ```

* Push Google Container Registry
    ```bash

    docker tag website:latest gcr.io/csonic-labs/website:1.0.0
    docker push gcr.io/csonic-labs/website:1.0.0

    docker tag website:latest gcr.io/csonic-labs/website:2.0.0
    docker push gcr.io/csonic-labs/website:2.0.0

    gcloud auth login

    gcloud auth print-access-token
  
    docker login -u oauth2accesstoken -p "token!!" https://gcr.io

    docker push gcr.io/csonic-labs/website:1.0.0

    where [HOSTNAME] is gcr.io, us.gcr.io, eu.gcr.io, or asia.gcr.io.
    ```



* Pull images
    ```bash

    docker pull aldot25/website:2.0.0
    docker pull docker pull gcr.io/csonic-labs/website:2.0.0
    docker pull gcr.io/csonic-labs/website:2.0.0

    ```
