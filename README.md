# fred-13_microservices
fred-13 microservices repository

---------------------Homework13-----------------------

1) Создана ветка docker-2
2) Создан новый проект docker в GCP
3) Настроена синхронизация консоли с проектом в GCP
4) Установлен инструмент docker-machine
5) Запуск контейнера в GCP:

  docker-machine create --driver google \
    --google-machine-image https://www.googleapis.com/compute/v1/projects/ubuntu-os-cloud/global/images/family/ubuntu-1604-lts \
    --google-machine-type n1-standard-1 \
    --google-zone europe-west1-b \
    docker-host

6) Проверка успешности запуска хоста "$ docker-machine ls"
7) Практика из лекции ( PID namespace, net namespace, user namespaces )
8) Сборка образа на базе Dockerfile с помощью файлов в корне mongod.conf, db_config, start.sh
9) Разрешаем входящий трафик:

  gcloud compute firewall-rules create reddit-app \
   --allow tcp:9292 \
   --target-tags=docker-machine \
   --description="Allow PUMA connections" \
   --direction=INGRESS

10) Регистрация на Docker Hub и загрузка своего первого образа:

  $ docker login
  $ docker tag reddit:latest fred13/otus-reddit:1.0

11) Проверка этого образа как в GCP так и локально

-----------------------------------------------------


---------------------Homework12-----------------------

1) Создана ветка docker-1
2) Настроена интеграция с travis-ci
3) Создана директория docker-monolith
4) Установлен docker, docker-compose, docker-machine
5) Проработаны основные команды docker
6) Выполнено задание со *

-----------------------------------------------------
