University: [ITMO University](https://itmo.ru/ru/) \
Faculty: [FICT](https://fict.itmo.ru) \
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies) \
Year: 2023/2024 \
Group: K4111C \
Author: Detushev Artem R. \
Lab: Lab4 \
Date of create: 12.11.2023 \
Date of finished: ? 

# Лабораторная работа №4 "Сети связи в Minikube, CNI и CoreDNS"

## Содержание

- [Содержание](#содержание)
- [Введение](#введение)
- [Ход работы](#ход-работы)
  - [Создание Deployment](#создание-deployment)
  - [Создание Service](#создание-service)
- [Cхема](#схема)

## Введение

**Цель работы:**

Познакомиться с CNI Calico и функцией IPAM Plugin, изучить особенности работы CNI и CoreDNS.

**Задачи:**

- При запуске minikube установите плагин CNI=calico и режим работы Multi-Node Clusters одновеременно, в рамках данной лабораторной работы вам нужно развернуть 2 ноды.
- Проверьте работу CNI плагина Calico и количество нод, результаты проверки приложите в отчет.
- Для проверки работы Calico мы попробуем одну из функций под названием IPAM Plugin.
- Для проверки режима IPAM необходимо для запущеных ранее нод указать label по признаку стойки или географического расположения (на ваш выбор).
- После этого вам необходимо разработать манифест для Calico который бы на основе ранее указанных меток назначал бы IP адреса "подам" исходя из пулов IP адресов которые вы указали в манифесте.
- Вам необходимо создать deployment с 2 репликами контейнера ifilyaninitmo/itdt-contained-frontend:master и передать переменные в эти реплики: REACT_APP_USERNAME, REACT_APP_COMPANY_NAME.
- Создать сервис через который у вас будет доступ на эти "поды". Выбор типа сервиса остается на ваше усмотрение.
- Запустить в minikube режим проброса портов и подключитесь к вашим контейнерам через веб браузер.
- Проверьте на странице в веб браузере переменные Container name и Container IP. Изменяются ли они? Если да то почему?
- Используя kubectl exec зайдите в любой "под" и попробуйте попинговать "поды" используя FQDN имя соседенего "пода", результаты пингов необходимо приложить к отчету.

## Ход работы

**Создание СonfigMap**



![configmap](/image/?)

**Создание ReplicaSet**



![replicaset](/image/?)



![secret](/image/?)



![ingress](/image/?)

