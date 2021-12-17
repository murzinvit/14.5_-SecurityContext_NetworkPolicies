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

Результат после применения политики для контейнера 2: []() </br>
![](https://github.com/murzinvit/screen_1/blob/926e4813e51d97e419d88c4cfb0bb7dec6e925a3/Kuber_curl_from_n2_after_policy.jpg) </br>

---
### work notes
По умолчанию политика kubernetes - разрешить всё </br>
https://habr.com/ru/company/flant/blog/443190/ </br>

