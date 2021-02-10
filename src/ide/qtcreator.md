# QtCreator

## [Установка](https://doc.qt.io/qtcreator/creator-getting-started.html)
Есть мануал на официальном сайте (ссылка в header-e - кликабельна). [Здесь](https://www.qt.io/offline-installers) можно найти offline установщики Qt (в который собственно и входит Creator) для Windows и Linux/MacOS. 

На __Ubuntu__ рекомендуется следующий процесс установки (чтобы можно было обновлять среду разработки через пакетный менеджер):  
```console
$ sudo apt install qtcreator
```

## [clang-tidy](https://doc.qt.io/qtcreator/creator-clang-tools.html)
__QtCreator__ имеет встроенный *clang-tidy*, но вы можете указать внешний, если он есть на вашей системе.

> Чтобы использовать __.clang-tidy__ курса, к сожалению, нужно будет копипастнуть наш файлик в Edit checks as string (смотрите конец инструкции в header - e)

До настроек clang-tidy можно добраться через Tools -> Options -> Analyzer -> Diagnostic Configuration

![clang-tidy-qtcreator](images/clang-tidy-qtcreator.png)

Там нужно будет создать копию и нажать Edit checks as string, куда вставить содержимое нашего файлика.

![clang-tidy-qtcreator-2](images/clang-tidy-qtcreator-2.png)


## [clang-format](https://doc.qt.io/qtcreator/creator-beautifier.html)

Для установки автоматического форматирования кода в __QtCreator__ нужен плагин Beautifier. О том как его установить можно почитать по ссылке.

> Рекомендуем поставить галочку на  `Enable auto format on file save`

После перезапуска QtCreator идем в Tools -> Options -> Beautifier -> ClangFormat. Если у вас не стоит clang-format, его нужно поставить, в Ubuntu это `sudo apt install clang-format`. Далее в Options в `Use predefinde styles` выбираем опцию `File` вместо `LLVM`

![clang-format-qtcreator](images/clang-format-qtcreator.png)

