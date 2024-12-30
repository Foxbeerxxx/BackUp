# Домашнее задание к занятию "`Резервное копирование`" - `Татаринцев Алексей`



---

### Задание 1

`Резервное копирование`

1. `Составляем данную команду для зеркального копирования`
```
rsync -a --delete --checksum --exclude='*/.*' /home/Alexey/ /tmp/backup/
```
![1](https://github.com/Foxbeerxxx/BackUp/blob/main/img/img1.png)`

2. `Проверяю : смотрим , что по каталогам`
```
ls -l /tmp/backup

```
![2](https://github.com/Foxbeerxxx/BackUp/blob/main/img/img2.png)`

3. `Смотрим все содержимое`
```
ls -la /tmp/backup

```
![3](https://github.com/Foxbeerxxx/BackUp/blob/main/img/img3.png)`




---

### Задание 2

`Для выполнения данного задания я буду использовать rsync для создания зеркальных резервных копий, и cron для автоматического выполнения этой задачи раз в день. Также сделаю так, чтобы результат выполнения скрипта записывался в системный лог с помощью команды logger,если вдруг будет ошибка можно будет проанализировать.`

1. `Создаю скрипт с именем backup.sh в домашней директории и прописываем наполнение`

![4](https://github.com/Foxbeerxxx/BackUp/blob/main/img/img4.png)`
2. `Делаю скрипт исполняемым`
```
chmod +x ~/backup.sh
```

3. `Настройка cron, запускаю редактор задач`
```
crontab -e
```
4. `Добавляю в коней следующее выражение`
```
0 2 * * * /home/alexey/backup.sh
```
![5](https://github.com/Foxbeerxxx/BackUp/blob/main/img/img5.png)`
`Эта строчка означает, что скрипт будет выполняться каждый день в 2 часа ночи.`
5. `Для проверки можно временно изменить расписание в файле crontab, чтобы скрипт выполнялся, например, каждую минуту:`
```
* * * * * /home/alexey/backup.sh
```

![6](https://github.com/Foxbeerxxx/BackUp/blob/main/img/img6.png)`

6. `Если глянуть логи, то понятно, что мой скрипт отрабатывает:`
![7](https://github.com/Foxbeerxxx/BackUp/blob/main/img/img7.png)`
