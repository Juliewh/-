# Лабораторная работа
## Задание 1
1. Создаем файл ```logfile.txt```

```
echo -e "2024-01-01 10:00:00 INFO: System boot completed.\n2024-01-01 10:15:32 WARNING: Disk space low on /dev/sda1.\n2024-01-01 11:00:45 ERROR: Failed to start service X.\n2024-01-02 09:12:11 INFO: User login detected.\n2024-01-02 09:15:50 INFO: User logout detected.\n2024-01-02 09:30:00 ERROR: Network timeout occurred.\n2024-01-03 12:00:00 INFO: Backup started.\n2024-01-03 12:15:00 WARNING: High CPU usage detected.\n2024-01-04 08:00:00 INFO: Scheduled task executed.\n2024-01-04 08:30:00 ERROR: Failed to execute task Y.\n2024-01-05 18:00:00 INFO: Shutdown initiated." > logfile.txt
```
![изображение](https://github.com/user-attachments/assets/732d9dc5-e123-43dc-adca-74b38a5b84b6)


2. Находим все строки, содержищие слово ```ERROR```:

```
grep "ERROR" logfile.txt
```

3. Выводим строки, в которых есть либо ```WARNING```, либо ```ERROR```:

```
grep -E "WARNING|ERROR" logfile.txt
```

4. Ищем строки, содержащие ```INFO```, но не содержащие ```User```:

```
grep "INFO" logfile.txt | grep -v "User"
```
![изображение](https://github.com/user-attachments/assets/c71c4386-89e0-4042-8a8b-679b2e4cc77c)

5. Находим все события, произошедшие ```1 января 2024 года```:

```
grep "2024-01-01" logfile.txt
```

6. Находим строки, в которых время события назодится между ```09:00:00``` и ```10:00:00``` (включительно):

```
grep -E "09:[0-5][0-9]:[0-5][0-9]|10:00:00" logfile.txt
```

7. Выведем все ошибки ```(ERROR)``` за ```4 января 2024 года```:

```
grep "2024-01-04" logfile.txt | grep "ERROR"
```
![изображение](https://github.com/user-attachments/assets/c58dd864-4330-4b8b-a6f2-130a69305a66)

8. Найдем строки, где упоминается путь к устройствам, например, ```dev/sda1```:

```
grep "/dev/sda1" logfile.txt
```

9. Выведем строки, где упоминается ```service X``` или ```task Y```, независимо от регистра:

```
grep -iE "service X|task Y" logfile.txt
```
![изображение](https://github.com/user-attachments/assets/f95ff77d-db22-4f28-8bc5-f725d02a9ae7)

10. Подсчитаем количество строк
