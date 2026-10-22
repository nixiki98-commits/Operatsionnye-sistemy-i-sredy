# Домашнее задание: Использование простых команд

**Студент:** Ярушевский Никита  
**Группа:** РПО26/11/1  
**Преподаватель:** Штейнберг Эмиль Эдуардович

## Задания

### 1. Файлы .log в /var/log
```bash
ls /var/log/*.log
```
<img width="495" height="117" alt="image" src="https://github.com/user-attachments/assets/edda9bb4-e42f-4219-8a75-96ecfc8e6166" />

### 2. Файлы /usr/bin по размеру
```bash
ls -lS
```
<img width="535" height="767" alt="image" src="https://github.com/user-attachments/assets/e3af9aad-896f-42ce-bcc2-06a42a021007" />

### 3. Содержимое sources.list
```bash
cat /etc/apt/sources.list
```
<img width="953" height="37" alt="image" src="https://github.com/user-attachments/assets/7a941c5a-9ca8-4793-930a-ae6b1c768527" />

### 4. Строки с root в /etc/passwd
```bash
grep root /etc/passwd
```

### 5. Строки без комментариев в /etc/services
```bash
grep -v '^#' /etc/services | grep -v '^$'
```
<img width="505" height="798" alt="image" src="https://github.com/user-attachments/assets/0494a9a5-a94b-483b-ba53-fabc37ce36ad" />

### 6. Файлы *.conf в /etc
```bash
find /etc \( -name "*.conf" -o -name "*.conf.d" \)
```
<img width="432" height="602" alt="image" src="https://github.com/user-attachments/assets/7dcb72ee-ace1-4402-9b7b-5ed1039f362f" />

### 7. Символические ссылки в корне
```bash
find / -maxdepth 1 -type l | wc -l
```
<img width="447" height="562" alt="image" src="https://github.com/user-attachments/assets/da9e3986-0fd6-4692-b2ea-a14246418ec5" />

### 8. Каталоги в /usr/share
```bash
find /usr/share -maxdepth 2 -type d
```
<img width="277" height="817" alt="image" src="https://github.com/user-attachments/assets/75509d28-d814-4b3e-a56f-9b0164eec4ee" />

### 9. Файлы в /var от root
```bash
find /var -user root -type f
```
<img width="782" height="832" alt="image" src="https://github.com/user-attachments/assets/7f532b2b-8953-4d90-9ca6-7e1a5ac5ef6c" />

### 10. Файлы в /etc с root
```bash
find /etc -maxdepth 2 -type f -exec grep -l root {} \;
```
<img width="325" height="587" alt="image" src="https://github.com/user-attachments/assets/4afc5b2a-5c3d-451a-b55a-8ff8c4dc615e" />

## Вывод
В процессе выполнения домашнего задания изучены команды ls, cat, grep и find. Освоены фильтрация с grep -v, поиск файлов по имени и владельцу, комбинация find с grep через -exec.
