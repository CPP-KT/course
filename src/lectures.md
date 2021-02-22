# План лекций

## Лекция 1 [^zubkov]
Видео [1](https://www.youtube.com/watch?v=XA7MgOfJ45g&list=PLd7QXkfmSY7a2zw_PVPn7vKs9F9BG6Pd4&index=1), [2](https://www.youtube.com/watch?v=B3o7gt1o_cI&list=PLd7QXkfmSY7a2zw_PVPn7vKs9F9BG6Pd4&index=2). Презентация [pdf](lecture-1f.pdf), [odf](lecture-1f.odf).

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

## Лекция 2 [^zubkov]
Видео [1](https://www.youtube.com/watch?v=BBruh_iOxjY&list=PLd7QXkfmSY7a2zw_PVPn7vKs9F9BG6Pd4&index=3), [2](https://www.youtube.com/watch?v=i8jYRexvORg&list=PLd7QXkfmSY7a2zw_PVPn7vKs9F9BG6Pd4&index=4). Презентация [pdf](lecture-2c.pdf), [odf](lecture-2c.odf).

* регистр SP и команды для работы со стеком (push, pop)
* команды call и ret
* передача параметров через стек, чистка стека от параметров
* соглашения вызова функций [^agner_fog_calling_conventions]
* регистр BP, стековый фрейм [^eli_bendersky_stackframe_layout] [^adam_langley_cfe_directives]

## Лекция 3

* кеш-память [^ulrich_drepper_memory] [^tony_albrecht_pitfalls] [^paul_mckenney_mem_barriers]
* translation lookaside buffer
* спекулятивное исполнение команд [^yann_collet] [^popcount]
* branch prediction [^branch_prediction_stackoverflow]
* выравнивание

[^zubkov]: С. В. Зубков — Assembler для DOS, Windows, UNIX

[^hackers_delight]: Henry S. Warren, Jr. — Hacker's Delight

[^agner_fog_calling_conventions]: [Agner Fog — Calling conventions for different C++ compilers and operating systems](http://www.agner.org/optimize/calling_conventions.pdf)

[^eli_bendersky_stackframe_layout]: [Eli Bendersky — Stack frame layout on x86-64](http://eli.thegreenplace.net/2011/09/06/stack-frame-layout-on-x86-64)

[^adam_langley_cfe_directives]: [Adam Langley — CFI directives in assembly files](https://www.imperialviolet.org/2017/01/18/cfi.html)

[^ulrich_drepper_memory]: [Ulrich Drepper — What Every Programmer Should Know About Memory](http://people.redhat.com/drepper/cpumemory.pdf)

[^tony_albrecht_pitfalls]: [Tony Albrecht — Pitfalls of Object Oriented Programming](http://research.scee.net/files/presentations/gcapaustralia09/Pitfalls_of_Object_Oriented_Programming_GCAP_09.pdf)

[^paul_mckenney_mem_barriers]: [Paul E. McKenney — Memory Barriers: A Hardware View for Software Hackers](http://www.rdrop.com/users/paulmck/scalability/paper/whymb.2010.06.07c.pdf)

[^yann_collet]: [Yann Collet — Counting bytes fast — little trick from FSE](http://fastcompression.blogspot.ru/2014/09/counting-bytes-fast-little-trick-from.html)

[^popcount]: [POPCOUNT false dependency bug](https://stackoverflow.com/questions/25078285/replacing-a-32-bit-loop-count-variable-with-64-bit-introduces-crazy-performance)

[^branch_prediction_stackoverflow]: [Why is processing a sorted array faster than processing an unsorted array?](https://stackoverflow.com/questions/11227809/why-is-processing-a-sorted-array-faster-than-processing-an-unsorted-array)
