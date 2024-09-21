# Основы обработки данных с помощью R и Dplyr
Выполнено Зайцевым Ильей Владимировичем, mragentseven@yandex.ru

# Лабораторная работа №2

## Цель работы

1.  Развить практические навыки использования языка программирования R
    для обработки данных
2.  Закрепить знания базовых типов данных языка R
3.  Развить практические навыки использования функций обработки данных
    пакета dplyr – функции select(), filter(), mutate(), arrange(),
    group_by()

## Ход выполнения работы

Загружаем необходимую библиотеку

    ::: {.cell}

    ```{.r .cell-code}
    library(dplyr)
    ```

    ::: {.cell-output .cell-output-stderr}

    ```

    Attaching package: 'dplyr'
    ```


    :::

    ::: {.cell-output .cell-output-stderr}

    ```
    The following objects are masked from 'package:stats':

        filter, lag
    ```


    :::

    ::: {.cell-output .cell-output-stderr}

    ```
    The following objects are masked from 'package:base':

        intersect, setdiff, setequal, union
    ```


    :::
    :::

1.  Сколько строк в датафрейме?

<!-- -->

    ::: {.cell}

    ```{.r .cell-code}
    starwars %>% nrow()
    ```

    ::: {.cell-output .cell-output-stdout}

    ```
    [1] 87
    ```


    :::
    :::

1.  Сколько столбцов в датафрейме?

<!-- -->

    ::: {.cell}

    ```{.r .cell-code}
    starwars %>% ncol()
    ```

    ::: {.cell-output .cell-output-stdout}

    ```
    [1] 14
    ```


    :::
    :::

1.  Как просмотреть примерный вид датафрейма?

<!-- -->

    ::: {.cell}

    ```{.r .cell-code}
    starwars %>% glimpse()
    ```

    ::: {.cell-output .cell-output-stdout}

    ```
    Rows: 87
    Columns: 14
    $ name       <chr> "Luke Skywalker", "C-3PO", "R2-D2", "Darth Vader", "Leia Or…
    $ height     <int> 172, 167, 96, 202, 150, 178, 165, 97, 183, 182, 188, 180, 2…
    $ mass       <dbl> 77.0, 75.0, 32.0, 136.0, 49.0, 120.0, 75.0, 32.0, 84.0, 77.…
    $ hair_color <chr> "blond", NA, NA, "none", "brown", "brown, grey", "brown", N…
    $ skin_color <chr> "fair", "gold", "white, blue", "white", "light", "light", "…
    $ eye_color  <chr> "blue", "yellow", "red", "yellow", "brown", "blue", "blue",…
    $ birth_year <dbl> 19.0, 112.0, 33.0, 41.9, 19.0, 52.0, 47.0, NA, 24.0, 57.0, …
    $ sex        <chr> "male", "none", "none", "male", "female", "male", "female",…
    $ gender     <chr> "masculine", "masculine", "masculine", "masculine", "femini…
    $ homeworld  <chr> "Tatooine", "Tatooine", "Naboo", "Tatooine", "Alderaan", "T…
    $ species    <chr> "Human", "Droid", "Droid", "Human", "Human", "Human", "Huma…
    $ films      <list> <"A New Hope", "The Empire Strikes Back", "Return of the J…
    $ vehicles   <list> <"Snowspeeder", "Imperial Speeder Bike">, <>, <>, <>, "Imp…
    $ starships  <list> <"X-wing", "Imperial shuttle">, <>, <>, "TIE Advanced x1",…
    ```


    :::
    :::
