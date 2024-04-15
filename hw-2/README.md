# Практическая работа №2 “Использование Kubernetes”

Для сборки и запуска кластера требуется установленный kubectl и minikube.

Инструкция по установке kubectl в Linux есть [тут](https://kubernetes.io/ru/docs/tasks/tools/install-kubectl/#%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-%D0%B1%D0%B8%D0%BD%D0%B0%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D1%84%D0%B0%D0%B9%D0%BB%D0%B0-kubectl-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-curl-%D0%B2-linux).

Инструкция по установке minikube в Linux есть [тут](https://kubernetes.io/ru/docs/tasks/tools/install-minikube/#%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-minikube-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-%D0%BF%D1%80%D1%8F%D0%BC%D0%BE%D0%B9-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8).

## Доступные команды

Запуск кластера с приложением:
```bash
make all
```

Удаление кластера с приложением:
```bash
make clean
```

Вывести ip-адрес приложения:
```bash
make get_ip
```

Запуск dashboard:
```bash
minikube dashboard
```
