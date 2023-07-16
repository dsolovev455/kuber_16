# Домашнее задание к занятию «Как работает сеть в K8s»

1. Создан кластер с сетевым плагином Calico:  
   ![calico](./pictures/calico.PNG)  
   Из [manifest файла](./files/deployment.yaml) в default namespace развёрнуты деплойменты для frontend, backend, и cache:  
   ![pods](./pictures/pods.PNG)  
   На default namespace применен [manifest файл](./files/network-policy.yaml) сетевых политик запрещающий весь трафик кроме трафика от frontend к backend и от backend к cache:  
   ![networkPolicy](./pictures/networkPolicy.PNG)  
   C fronend команда curl отрабатывает только до backend:  
   ![frontend](./pictures/frontend.PNG)  
   С backend команда curl отрабатывает только до cache:  
   ![backend](./pictures/backend.PNG)  
   С cache команда curl не отрабатывает ни на один адрес:  
   ![cache](./pictures/cache.PNG)  