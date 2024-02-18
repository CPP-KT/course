# Установка и настройка окружения на Mac для практик и домашних заданий на ассемблере x86_64

План действий эмуляции x86_64 и запуска edb-debugger и ассемблера.

## Установка UTM и эмуляция x86_64
Необходимо скачать и установить [UTM](https://mac.getutm.app), а так же образ [ubuntu](https://ubuntu.com/download/desktop), в целом можно и другой образ.

Далее добавляем виртуальную машину в UTM, если у вас apple silicon, т.e. на архитектуре ARM, выбираем emulate, если у вас mac на intel, можно выбрать любую опцию, но быстрее будет virtualize. После следуем по всем шагам установки и настраиваем под себя.
Так же для более плавной работы в настройках виртуальной машины можно увеличить количество ядер и прожать опцию Force multicore.

## Настройка ubuntu и установка утилит
Обновляем систему и пакеты
```bash
sudo apt update && sudo apt upgrade
```
Для практики по ассемблеру, вам понадобятся `nasm` и дебаггер `edb`, установите их при помощи следующей команды:
```bash
sudo apt install nasm binutils edb-debugger xterm
```

Для проверки работоспособности напишите `edb` в консоль, после чего он должен открыться в отдельном окне.

Если у вас вылез данный warning:
```bash
Warning: Ignoring XDG_SESSION_TYPE=wayland on Gnome. Use QT_QPA_PLATFORM=wayland to run on Wayland anyway.
```
Может помочь прописать:
```bash
export QT_QPA_PLATFORM=wayland
sudo apt install qtwayland5
```
