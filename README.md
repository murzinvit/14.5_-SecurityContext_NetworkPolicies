### Задача 1: Рассмотрите пример 14.5/example-security-context.yml
Создайте модуль
```
kubectl apply -f 14.5/example-security-context.yml
```

Проверьте установленные настройки внутри контейнера
```
kubectl logs security-context-demo
uid=1000 gid=3000 groups=3000
```
![](https://github.com/murzinvit/screen_1/blob/5027a83ffe84403e5cc2cb87cc6c12e82c614003/Kuber_run_context.jpg) </br>

### Задача 2 (*): Рассмотрите пример 14.5/example-network-policy.yml
Создайте два модуля. Для первого модуля разрешите доступ к внешнему миру
и ко второму контейнеру. Для второго модуля разрешите связь только с
первым контейнером. Проверьте корректность настроек.

Политика для Pod_1: [nginx_1_policy.yaml](https://github.com/murzinvit/14.5_SecurityContext_NetworkPolicies/blob/65cc0c1edb1844613a296dace474250a52ab2b1c/nginx_1_policy.yaml) </br>
Политика для Pod_2: [nginx-2-policy.yaml](https://github.com/murzinvit/14.5_SecurityContext_NetworkPolicies/blob/da3233dcee7af47c8b19e75b902754fb539914e4/nginx-2-policy.yaml) </br>
Результат после применения NetworkPolicy для Pod_2. На IP адрес Pod_1 curl возможен, на mail.ru - нет: </br>
![](https://github.com/murzinvit/screen_1/blob/926e4813e51d97e419d88c4cfb0bb7dec6e925a3/Kuber_curl_from_n2_after_policy.jpg) </br>
Результат после применения NetworkPolicy для контейнера Pod_1. На IP Pod_2 curl возможен, mail.ru также доступен: </br>
![](https://github.com/murzinvit/screen_1/blob/de8c90ba4923144c95dabdc3ab7a532b1ebfe04c/Kuber_get_policy_front.jpg) </br>

---
### work notes
По умолчанию политика kubernetes - разрешить всё </br>
https://habr.com/ru/company/flant/blog/443190/ </br>

