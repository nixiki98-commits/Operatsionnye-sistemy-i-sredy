# Домашнее задание: Функции в Bash

**Студент:** Ярушевский Никита  
**Группа:** РПО26/11/1  
**Преподаватель:** Штейнберг Эмиль Эдуардович

## Задание 1. Функция вывода в поток

```bash
print_to() {
  local text="$1"
  local dest="$2"
  case "$dest" in
    stdout) echo "$text" ;;
    stderr) echo "$text" >&2 ;;
    *)      echo "$text" > "$dest" ;;
  esac
}
```

## Задание 2. Функция sysinfo

```bash
sysinfo() {
  case "$1" in
    pwd)     pwd ;;
    user)    whoami ;;
    version) uname -a ;;
    date)    date ;;
    *)       echo "Unknown: $1" ;;
  esac
}
```

## Задание 3. Функция через eval

```bash
show_var() {
  local name="$1"
  eval "echo \$$name"
}
while read -r varname; do
  show_var "$varname"
done
```

## Ответ: exit и return

**exit** завершает весь скрипт. **return** завершает только функцию; скрипт продолжает работу.

## Вывод
Освоены функции в Bash: определение, local, аргументы $1/$2, return. Понята разница exit и return.
