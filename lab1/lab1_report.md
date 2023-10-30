University: [ITMO University](https://itmo.ru/ru/) \
Faculty: [FICT](https://fict.itmo.ru) \
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies) \
Year: 2023/2024 \
Group: K4111C \
Author: Detushev Artem R. \
Lab: Lab1 \
Date of create: 30.10.2023 \
Date of finished:  \

# Лабораторная работа №1 "Установка Docker и Minikube, мой первый манифест."

## Содержание

- [Содержание](#содержание)
- [Введение](#введение)
- [Ход работы](#ход-работы)
  - [Установка Docker/Minikube](#установка-dockerminikube)
  - [Создание пода](#создание-пода)
  - [Получение токен](#получение-токена)
- [Cхема](#схема)

## Введение

**Цель работы**: \
Ознакомиться с инструментами Minikube и Docker, развернуть свой первый "под".
**Задачи** \

- Установить Docker/Minikube
- Создать под Vault и получить к нему доступ к контейнеру
- Найти сгенерированный Root токен, чтобы получить доступ к Vault

## Ход работы

### Установка Docker/Minikube

Для выполнения лабораторной работы использовался установленный Docker Desktop для Windows. \
Помимо этого по [оригинальной инструкции](https://minikube.sigs.k8s.io/docs/start/) был установлен minikube.
С помощью команды minikube start, будет запущен minikube.

![minikube-start](images\minikube-start.png)

### Создание пода

Для создания пода был создан манифест, который можно найти в файле **vault-pod.yaml**.
После этого был создан сервис для доступа к контейнеру c портом 8200 с помощью команды minikube kubectl -- expose pod vault --type=NodePort --port=8200.
Используя команду minikube kubectl -- port-forward service/vault 8200:8200, мы прокидываем тунель от локальной машины до контейнера.

![port-forward](images\port-forward.png)

Выполнив все команды, мы получили доступ к Vault.

![web-vault](images\web-vault.jpeg)

### Получение токена

Токен от Vault находится в логах. 
Для того что бы увидеть логи необходимо воспользоваться командой kubectl logs (имя пода). В моём случае это kubectl logs vault.
![logs](images\logs.png)

Скопируем данный токен и вставим в форму, тем самым получив доступ к функциональности Vault.

## Схема

![scheme](images\scheme.png)