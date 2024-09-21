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

``` r
library(dplyr)
```


    Attaching package: 'dplyr'

    The following objects are masked from 'package:stats':

        filter, lag

    The following objects are masked from 'package:base':

        intersect, setdiff, setequal, union

Сколько строк в датафрейме?

``` r
starwars %>% nrow()
```

    [1] 87

Сколько столбцов в датафрейме?

``` r
starwars %>% ncol()
```

    [1] 14

Как просмотреть примерный вид датафрейма?

``` r
starwars %>% glimpse()
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

Сколько уникальных рас персонажей (species) представлено в данных?

``` r
starwars %>%
  distinct(species) %>%
  nrow()
```

    [1] 38

Найти самого высокого персонажа.

``` r
starwars %>%
  arrange(desc(height)) %>%
  slice_head(n = 1) %>%
  select(name, height)
```

    # A tibble: 1 × 2
      name        height
      <chr>        <int>
    1 Yarael Poof    264

Найти всех персонажей ниже 170.

``` r
starwars %>%
  filter(height < 170) %>%
  select(name, height)
```

    # A tibble: 22 × 2
       name                  height
       <chr>                  <int>
     1 C-3PO                    167
     2 R2-D2                     96
     3 Leia Organa              150
     4 Beru Whitesun Lars       165
     5 R5-D4                     97
     6 Yoda                      66
     7 Mon Mothma               150
     8 Wicket Systri Warrick     88
     9 Nien Nunb                160
    10 Watto                    137
    # ℹ 12 more rows

Подсчитать ИМТ (индекс массы тела) для всех персонажей. ИМТ подсчитать
по формуле.

``` r
starwars %>%
  mutate(bmi = mass / (height / 100)^2) %>%
  select(name, height, mass, bmi)
```

    # A tibble: 87 × 4
       name               height  mass   bmi
       <chr>               <int> <dbl> <dbl>
     1 Luke Skywalker        172    77  26.0
     2 C-3PO                 167    75  26.9
     3 R2-D2                  96    32  34.7
     4 Darth Vader           202   136  33.3
     5 Leia Organa           150    49  21.8
     6 Owen Lars             178   120  37.9
     7 Beru Whitesun Lars    165    75  27.5
     8 R5-D4                  97    32  34.0
     9 Biggs Darklighter     183    84  25.1
    10 Obi-Wan Kenobi        182    77  23.2
    # ℹ 77 more rows
