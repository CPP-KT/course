# IDE и пакетный менеджер

## IDE

Вы можете использовать __IDE__ по вкусу для выполнения практик/домашних заданий.

> Но чтобы ваш код был в определенном стиле и при написании кода вы быстро увидели опечатки/минорные баги - вам предоставлены __.clang-tidy__ и __.clang-format__ файлы в репозиториях.

В подразделах описаны этапы конфигурации некоторых __IDE__ (рекомендуется __Clion__).

## Пакетный менеджер

Пакетный менеджер нужен для упраления зависимостями в проекте. В рамках данного курса мы будет использовать для этих целей vcpkg.

vcpkg - это не только инструмент, но и репозиторий с рецептами пакетов, который нужно склонировать.
```bash
git clone https://github.com/microsoft/vcpkg
./vcpkg/bootstrap-vcpkg.sh
```
или `.\vcpkg\bootstrap-vcpkg.bat` для Windows

Далее будет удобно добавить `./vcpkg/vcpkg` в `PATH`:
```bash
sudo ln -s "$(pwd)/vcpkg/vcpkg" /usr/bin/vcpkg
```

Самая главная команда vcpkg:
```bash
vcpkg help
```

Чтобы узнать список установленных библиотек, используйте:
```bash
vcpkg list
```

Для поиска конкретного пакета можно воспользоваться `vcpkg search`, например:
```bash
vcpkg search benchmark
benchmark                1.6.0#1          A library to support the benchmarking of functions, similar to unit-tests.
celero                   2.8.2#1          Celero is a modern cross-platform (Windows, Linux, MacOS) Microbenchmarkin...
hayai                    2019-08-10#1     C++ benchmarking framework
...
```
Поиск рецептов будет осуществляется в скачанном репозитории, так что если ваши рецепты устарели - сделайте `git pull`.

Чтобы обновить пакеты помогут команды `vcpkg update` и `vcpkg upgrade`. Обновите **установленные** пакеты:
```bash
vcpkg upgrade --no-dry-run
```

Установить пакет можно при помощи команды `vcpkg install`:
```bash
vcpkg install benchmark
```
Эта команда по умолчанию соберёт выбранный пакет в Release и Debug конфигурациях. Чтобы понять что и как будет собираться для выбранного пакета, можно заглянуть `./vcpkg/ports/PACKAGE_NAME`. Чтобы понять в какой конфигурации &mdash; ознакомьтесь с `vcpkg help triplets`, а также со скриптами триплетов, которые находятся в `./vcpkg/triplets/`.
По умолчанию на Windows используется MS тулчейн (MSVC/clang-cl), для работы с MinGW нужно явно указать параметр `--triplet=x64-mingw-dynamic` при выполнении `vcpkg install`
После исполнения команды, вам скорее всего подскажут как использовать этот пакет, вроде:
```CMake
find_package(benchmark CONFIG REQUIRED)
target_link_libraries(main PRIVATE benchmark::benchmark benchmark::benchmark_main)
```
Если вы повторите команду `vcpkg install`, то он напишет, что пакет установлен, и продублирует сообщение `find_package(...`. И если вы добавите этот код в ваш CMakeLists.txt, то ничего не заработает!

Нужно подсказать CMake где хранятся find-package скрипты из vcpkg. Для этого используется следующий флаг при конфигурации cmake (`D:\src\vcpkg` в данном примере в качестве полного путь до `vcpkg` директории, **замените на свой!**):
```bash
-DCMAKE_TOOLCHAIN_FILE=D:\src\vcpkg\scripts\buildsystems\vcpkg.cmake
```

Также, если вы пользуетесь Windows нативно (т.е. не WSL), нужно добавить `-DVCPKG_TARGET_TRIPLET=x64-mingw-static` для тулчейна MinGW и `-DVCPKG_TARGET_TRIPLET=x64-windows-static` для тулчейна MSVC/clang-cl

В дополнение к ручной остановке пакетов можно в каждом проекте создать манифест в файле `vcpkg.json`, в котором явно перечисляются все зависимости. CMake, интегрированный с vcpkg, как было показано выше, в таком случае сам установит и соберёт все необходимые зависимости. В нашем в курсе используется именно этот вариант.
