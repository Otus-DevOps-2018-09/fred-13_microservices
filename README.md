# fred-13_microservices
fred-13 microservices repository

---------------------Homework25-----------------------

[![Build Status](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices.svg?branch=kubernetes-5)](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices)

1) Создана ветка kubernetes-5
2) Развернут кластер k8s
3) Из Helm-чарта установлен ingress-контроллер nginx (EXTERNAL-IP добавлен в /etc/hosts)
4) Загружен локально и установлен из кастомного файла Prometheus
5) Исследование Targets на наличие ряда endpoint для сбора метрик
6) Проверка сбора метрик
7) Выполнение задания с включением метрик для node-exporter
8) Сбор метрик с приложения (разбивка конфигурации на job-ы post-endpoints, comment-endpoints, ui-endpoints)
9) Установка grafana с помощью helm
10) Визуализация дашбордов с помощью готовых шаблонов (Kubernetes cluster monitoring, Kubernetes Deployment metrics)
11) Настройка своих дашбордов в Grafana с механизма templating
12) Создание файлов деплоя в директории kubernetes/efk/ (fluentd-ds.yaml,fluentd-configmap.yaml,es-service.yaml,es-statefulSet.yaml,es-pvc.yaml)
13) Установка Kibana из helm чарта
14) Создание шаблона индекса и поиск логов во вкладке Discover

------------------------------------------------------


---------------------Homework24-----------------------

[![Build Status](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices.svg?branch=kubernetes-4)](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices)

1) Создана ветка kubernetes-4
2) Установка клиент-серверного приложения Helm и его серверную часть Tiller для подключения по API к Kubernetes
3) Создание пакетов Chart для каждого сервиса и описание в них Templates
4) Шаблонизация сущностей сервисов (name, release и т.д.)
5) Описание шаблонов в виде функций в Helper (_helpers.tpl)
6) Созданрие единого механизма управления зависимостями Chart reddit
7) Установка GitLab с с помощью Helm Chart из пакета Omnibus
8) Создание группы и проектов в них (post, ui, comment, reddit-deploy)
9) Настройка CI. Проверка работы Pipeline
10) Создание отдельного окружение в Kubernetes по коммиту в feature-бранч
11) Создание staging и production среды для работы приложения

------------------------------------------------------


---------------------Homework23-----------------------

[![Build Status](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices.svg?branch=kubernetes-3)](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices)

1) Создана ветка kubernetes-3
2) Определение сетевого взаимодействия с помощью Service (kube-dns, kubenet, nodePort, LoadBalancer, Ingress)
3) Защита сервиса с помощью TLS (TLS Termination)
4) Работа с Network Policy в GKE (определение доступов между сервисами)
5) Работа с хранилищем для базы данных в GCE - reddit-mongo-disk

------------------------------------------------------


---------------------Homework22-----------------------

[![Build Status](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices.svg?branch=kubernetes-2)](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices)

1) Создана ветка kubernetes-2
2) Установлены: утилита kubectl и локальный гипервизор Minikube
3) Описание сервисов ui, comment, post, mongodb в блоке deployment
4) Запуск данных сервисов в Minikube (вывод сервиса ui путем port-forward)
5) Для взаимодействия сервисов друг с другом описываем новые объекты Service
6) Открываем доступ из вне с помощью NodePort
7) Изучение основных возможностей в Minikube (Namespace, Dashboard)
8) Сборка кластера в GKE
9) Запуск приложения reddit (namespace dev) в GKE
10) Активация и доступ к kubernetes-dashboard в GKE

------------------------------------------------------



---------------------Homework21-----------------------

[![Build Status](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices.svg?branch=kubernetes-1)](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices)

1) Создана ветка kubernetes-1
2) Описание Deployment файлов reddit сервисов в директории kubernetes/reddit
3) Проделана работа по туториалу от инженера из Google - Kelsey Hightower

------------------------------------------------------

---------------------Homework20-----------------------

[![Build Status](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices.svg?branch=logging-1)](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices)

1) Создана ветка logging-1
2) Собраны образы ui, post и comment при помощи скриптов docker_build.sh
3) Создан Docker хост в GCP
4) Создан отдельный compose-файл docker-compose-logging.yml для нашей системы логирования
5) Собран docker image для fluentd
6) Просмотр логов post сервиса путем:
```
docker-compose logs -f post
```
7) Запуск системы лоигрования путем:
```
$ docker-compose -f docker-compose-logging.yml up -d
$ docker-compose down
$ docker-compose up -d
```
8) Изучение инструмента Kibana для визуализации и анализа логов
9) Настройка фильтров и парсинга (fluentd)
10) Описание compose-файла docker-compose-logging.yml для сервисов логирования распределенного трейсинга Zipkin
11) Изучение инструмента Zipkin

------------------------------------------------------


---------------------Homework19-----------------------

[![Build Status](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices.svg?branch=monitoring-2)](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices)

1) Создана ветка monitoring-2
2) Создал Docker хост в GCE (docker-host)
3) Выделил в отдельный файл docker-compose-monitoring.yml описание мониторинга
4) Добавил новый сервис мониторинга cAdvisor в файл мониторинга
5) Открыл порт 8080 для cAdvisor во вне на GCP (firewall)
6) Пересобрал образ Prometheus
7) Запустил проект и проверил сбор метрик
8) Для визуализации данных из Prometheus добавил новый сервис grafana
9) Создал дашборд путем импорта готового решения с оф.сайта (DockerMonitoring.json)
10) Добавил информацию о post сервисе в конфигурацию Prometheus для сбора метрик с этого сервиса
11) Создал два дашборда в grafana по сборам метрик (UI_Service_Monitoring, Business_Logic_Monitoring)
12) Собрал образ alertmanager и настроил алертинг в канал в slack (проверка: [FIRING:1] InstanceDown (post:5000 post page))
13) Запушил все собранные docker образы в DockerHub. [Ссылка на образы тут](https://hub.docker.com/u/fred13)

------------------------------------------------------

---------------------Homework18-----------------------

[![Build Status](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices.svg?branch=monitoring-1)](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices)

1) Создана ветка monitoring-1
2) Создал правило фаервола для Prometheus и Puma:
```
$ gcloud compute firewall-rules create prometheus-default --allow tcp:9090
$ gcloud compute firewall-rules create puma-default --allow tcp:9292
```
3) Создал Docker хост в GCE
```
docker-machine create --driver google \
    --google-machine-image https://www.googleapis.com/compute/v1/projects/ubuntu-os-cloud/global/images/family/ubuntu-1604-lts \
    --google-machine-type n1-standard-1 \
    --google-zone europe-west1-b \
    docker-host
```
4) Загрузил готовый образ и запустил prometheus (знакомство с веб интерфейсом):
```
docker run --rm -p 9090:9090 -d --name prometheus prom/prometheus:v2.1.0
```
5) Создал директорию monitoring/prometheus и в ней описал Dockerfile для prometheus:
```
FROM prom/prometheus:v2.1.0
ADD prometheus.yml /etc/prometheus/
```
6) Создал файл prometheus.yml с описанием сбора метрик с наших микросервисов
7) Пересоздан образ:
```
$ docker build -t $USER_NAME/prometheus .
```
8) Собрал образы при помощи скриптов docker_build.sh:
```
/src/ui      $ bash docker_build.sh
/src/post-py $ bash docker_build.sh
/src/comment $ bash docker_build.sh
```
9) Поднял сервисы и просмотрел мониторинг состояния микросервисов
10) Подключил экспортер node-exporter описанием в docker/docker-compose.yml файле как сервис
11) Запушил образы на DockerHub. [Ссылка на образы тут](https://hub.docker.com/u/fred13)

------------------------------------------------------

---------------------Homework17-----------------------

[![Build Status](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices.svg?branch=gitlab-ci-2)](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices)

1) Создана ветка gitlab-ci-2
2) Поднят проект с прошлого ДЗ
3) Создан новый проект example2 в GitLab
4) Включил runner для этого проекта
5) Создано DEV-окружение
6) Определил два новых этапа stage и production как мануал
7) Затегировал код для выкатки в staging и production
8) Определил динамическое окружение

------------------------------------------------------

---------------------Homework16-----------------------

[![Build Status](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices.svg?branch=gitlab-ci-1)](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices)

1) Создана ветка gitlab-ci-1
2) Создана ВМ в GCP по требуемым параметрам
3) Установлен docker и docker-compose на ВМ
4) Запущен Gitlab CI в docker с помощью готового образа
4) Настроена группа и проект в Gitlab
5) Определение CI/CD Pipeline с помощью описания процесса в .gitlab-ci.yml
6) Регистрация и запуск Runner
7) Добавление тестирования приложения reddit в pipeline

------------------------------------------------------

---------------------Homework15-----------------------

[![Build Status](https://api.travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices.svg?branch=docker-4)](https://travis-ci.com/Otus-DevOps-2018-09/fred-13_microservices)

1) Создана ветка docker-4
2) Запуск контейнера с использованием none-драйвера из образа joffotron/docker-net-tools
3) Запуск контейнера в сетевом пространстве docker-хоста
4) Создание bridge-сети reddit в docker и запуск проекта в этой сети:
```
docker network create reddit --driver bridge
docker run -d --network=reddit mongo:latest
docker run -d --network=reddit fred13/post:1.0
docker run -d --network=reddit fred13/comment:1.0
docker run -d --network=reddit -p 9292:9292 ferd13/ui:1.0
```
5) Перезапуск проекта с новым сетевым alias (post_db, post, comment) для устранения ошибки связи контейнеров
6) Создание две docker-сети:
```
docker network create back_net --subnet=10.0.2.0/24
docker network create front_net --subnet=10.0.1.0/24
```
7) Действие из п.6 поломало общение фронта с бэком, поэтому подключим контейнеры ко второй сети:
```
docker network connect front_net post
docker network connect front_net comment
```
8) Просмотр iptables в docker-host
9) Установка docker-compose и запуск проекта с помощью этого инструмента:
```
export USERNAME=fred13
docker-compose up -d
docker-compose ps
```
10) Выполнение заданий для самостоятельной работы
11) Базвое имя проекта образуется по соотвествию директории из которой запускается docker-compose. Для того чтобы назвать по своему
необходимо в файл .env задать свой COMPOSE_PROJECT_NAME

------------------------------------------------------

---------------------Homework14-----------------------

1) Создана ветка docker-3
2) Скачинвание и распаковка архива microservices.zip ( microservices > src )
3) Создание докер файлов:

./post-py/Dockerfile
./comment/Dockerfile
./ui/Dockerfile

4) Скачивание последнего образа MongoDB и сборка образов с сервисами:

docker pull mongo:latest
docker build -t fred13/post:1.0 ./post-py
docker build -t fred13/comment:1.0 ./comment
docker build -t fred13/ui:1.0 ./ui

5) Создание изолированной сети и запуск контейнеров в ней:

docker network create reddit
docker run -d --network=reddit --network-alias=post_db --network-alias=comment_db mongo:latest
docker run -d --network=reddit --network-alias=post fred13/post:1.0
docker run -d --network=reddit --network-alias=comment fred13/comment:1.0
docker run -d --network=reddit -p 9292:9292 fred13/ui:1.0

6) Модификация содержимого ./ui/Dockerfile и пересборка контейнера ui, сравнение размеров:

REPOSITORY TAG     IMAGE ID      SIZE
fred13/ui  2.0   16a06056cc20    447MB
fred13/ui  1.0   8aa7c3bfc30e    780MB
   
7) Перезапуск приложения с новым контейнером ui (2.0)
8) В ходе выполнения пункта выше (7) потеряны данные, поэтому создадим Docker volume и подключим его к контейнеру mongo:latest:

docker volume create reddit_db
docker run -d --network=reddit --network-alias=post_db --network-alias=comment_db -v reddit_db:/data/db mongo:latest

После перезапуска контейнеров посты остаются на месте

------------------------------------------------------


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

------------------------------------------------------


---------------------Homework12-----------------------

1) Создана ветка docker-1
2) Настроена интеграция с travis-ci
3) Создана директория docker-monolith
4) Установлен docker, docker-compose, docker-machine
5) Проработаны основные команды docker
6) Выполнено задание со *

-----------------------------------------------------
