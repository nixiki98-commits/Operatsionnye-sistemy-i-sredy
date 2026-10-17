# Домашнее задание: Использование простых команд

**Студент:** Ярушевский Никита  
**Группа:** РПО26/11/1  
**Преподаватель:** Штейнберг Эмиль Эдуардович

## Задания

### 1. Файлы .log в /var/log
```bash
ls /var/log/*.log
```

### 2. Файлы /usr/bin по размеру
```bash
ls -lS
```

### 3. Содержимое sources.list
```bash
cat /etc/apt/sources.list
```

### 4. Строки с root в /etc/passwd
```bash
grep root /etc/passwd
```

### 5. Строки без комментариев в /etc/services
```bash
grep -v '^#' /etc/services | grep -v '^$'
```

### 6. Файлы *.conf в /etc
```bash
find /etc \( -name "*.conf" -o -name "*.conf.d" \)
```

### 7. Символические ссылки в корне
```bash
find / -maxdepth 1 -type l | wc -l
```

### 8. Каталоги в /usr/share
```bash
find /usr/share -maxdepth 2 -type d
```

### 9. Файлы в /var от root
```bash
find /var -user root -type f
```

### 10. Файлы в /etc с root
```bash
find /etc -maxdepth 2 -type f -exec grep -l root {} \;
```

## Вывод
В процессе выполнения домашнего задания изучены команды ls, cat, grep и find. Освоены фильтрация с grep -v, поиск файлов по имени и владельцу, комбинация find с grep через -exec.
