# Variant

> [Github Classrom](https://classroom.github.com/a/lnUHyt9_)

В этом задании вам нужно будет написать плюсовую вариацию алгебраических типов — [`variant`](https://en.cppreference.com/w/cpp/utility/variant)

По ссылке выше вы найдёте подробное описание данного класса со всеми функциями и вспомогательными структурами. Однако в рамках данного ДЗ вам необязательно реализовывать следующие его части:
* Конструкторы и операторы присваивания, включающие [`initializer_list`](https://en.cppreference.com/w/cpp/utility/initializer_list)
* [`monostate`](https://en.cppreference.com/w/cpp/utility/variant/monostate)
* Специализацию `std::hash`

Во время написания советуем обратить особое внимание на следующие вещи:
* Гарантии исключений
* `constexpr` возможности данного класса
* Тривиальность различных функций
