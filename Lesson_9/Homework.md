# Домашнее задание: Автоматизация сборки Unix Makefiles

**Студент:** Ярушевский Никита  
**Группа:** РПО26/11/1  
**Преподаватель:** Штейнберг Эмиль Эдуардович

## Задание 1. Подготовка

### 1.1. binutils
```bash
apt install -y binutils
```

### 1.2. main.s
Простой ассемблерный «Hello, World!».

## Задание 2. Makefile

```makefile
main.o: main.s
	as -o main.o main.s

main: main.o
	ld -o main main.o

clean:
	rm -f *.o

build: main clean

.PHONY: clean build
```

### Сборка
```bash
make build
./main
```
Вывод: Hello, World!

## Вывод
Makefile описывает цели и зависимости. make проверяет изменения и не перекомпилирует лишнее. Освоены as, ld, make, .PHONY.
