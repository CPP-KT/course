# План лекций

## Лекция 1 <sup>[[видео 1]](https://www.youtube.com/watch?v=XA7MgOfJ45g&list=PLd7QXkfmSY7a2zw_PVPn7vKs9F9BG6Pd4&index=1)</sup> <sup>[[видео 2]](https://www.youtube.com/watch?v=B3o7gt1o_cI&list=PLd7QXkfmSY7a2zw_PVPn7vKs9F9BG6Pd4&index=2)</sup> [^zubkov]

* i8086
* регистры общего назначения, регистр IP
* операция mov, понятие endian
* распространенные арифметические операции: add, sub, [i]mul, [i]div, inc, dec, neg
* битовые операции, сдвиги: not, and, or, xor, shl, shr, sar
* команды безусловных переходов
* регистр флагов и некоторые биты в нём (ZF, CF, OF, SF)
* команды условных переходов
* команды cmp и test
* i80386, 32-битные регистры
* операция lea
* деление на константу не используя, команду div [^hackers_delight]
* инструкции для длинной арифменики: adc, sbb

## Лекция 2 <sup>[[видео 1]](https://www.youtube.com/watch?v=BBruh_iOxjY&list=PLd7QXkfmSY7a2zw_PVPn7vKs9F9BG6Pd4&index=3)</sup> <sup>[[видео 2]](https://www.youtube.com/watch?v=i8jYRexvORg&list=PLd7QXkfmSY7a2zw_PVPn7vKs9F9BG6Pd4&index=4)</sup> [^zubkov]

* регистр SP и команды для работы со стеком (push, pop)
* команды call и ret
* передача параметров через стек, чистка стека от параметров
* соглашения вызова функций [^agner_fog_calling_conventions]
* регистр BP, стековый фрейм [^eli_bendersky_stackframe_layout] [^adam_langley_cfe_directives]

[^zubkov]: С. В. Зубков — Assembler для DOS, Windows, UNIX
[^hackers_delight]: Henry S. Warren, Jr. — Hacker's Delight
[^agner_fog_calling_conventions]: [Agner Fog — Calling conventions for different C++ compilers and operating systems](http://www.agner.org/optimize/calling_conventions.pdf)
[^eli_bendersky_stackframe_layout]: [Eli Bendersky — Stack frame layout on x86-64](http://eli.thegreenplace.net/2011/09/06/stack-frame-layout-on-x86-64)
[^adam_langley_cfe_directives]: [Adam Langley — CFI directives in assembly files](https://www.imperialviolet.org/2017/01/18/cfi.html)
