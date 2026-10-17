# Домашнее задание: Создание демонов

**Студент:** Ярушевский Никита  
**Группа:** РПО26/11/1  
**Преподаватель:** Штейнберг Эмиль Эдуардович

## Задание 1. Скрипт демона

Скрипт mydaemon.sh с logger, trap (SIGTERM/SIGINT) и sleep:
```bash
logger -p local3.info -t mydaemon "Daemon started"
trap cleanup SIGTERM SIGINT
while true; do
  logger -p local3.info -t mydaemon "Daemon is active"
  sleep 5
done
```

## Задание 2. Демон на стороне пользователя

### 2.1. Unit-файл
`~/.config/systemd/user/mydaemon.service`

### 2.2. Запуск
```bash
systemctl --user daemon-reload
systemctl --user start mydaemon
systemctl --user status mydaemon
```

### 2.3. Проверка syslog и остановка
```bash
grep mydaemon /var/log/syslog
systemctl --user stop mydaemon
```

## Задание 3. Демон на стороне системы

### 3.1. Системный unit
`/etc/systemd/system/mydaemon-sys.service` с User, WorkingDirectory, Install.

### 3.2. enable и start
```bash
systemctl daemon-reload
systemctl enable mydaemon-sys
systemctl start mydaemon-sys
```

### 3.3. disable
```bash
systemctl disable mydaemon-sys
```

## Вывод
Демон — фоновая программа. Научился создавать user и system unit-файлы systemd, управлять через systemctl.
