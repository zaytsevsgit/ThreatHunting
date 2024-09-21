# Основы обработки данных с помощью R и Dplyr
Выполнено Зайцевым Ильей Владимировичем, mragentseven@yandex.ru

# Лабораторная работа №2_2

## Цель работы

1.  Развить практические навыки использования языка программирования R
    для обработки данных
2.  Закрепить знания базовых типов данных языка R
3.  Развить практические навыки использования функций обработки данных
    пакета dplyr – функции select(), filter(), mutate(), arrange(),
    group_by()

## Шаги

1.  Устанавливаем dplyr \`\`\` \> install.packages(“tidyverse”)
    Installing package into
    ‘C:/Users/frenz/AppData/Local/R/win-library/4.4’ (as ‘lib’ is
    unspecified) also installing the dependencies ‘colorspace’, ‘bit’,
    ‘farver’, ‘labeling’, ‘munsell’, ‘RColorBrewer’, ‘viridisLite’,
    ‘rematch’, ‘bit64’, ‘prettyunits’, ‘backports’, ‘generics’, ‘blob’,
    ‘DBI’, ‘tidyselect’, ‘data.table’, ‘gtable’, ‘isoband’, ‘scales’,
    ‘gargle’, ‘uuid’, ‘cellranger’, ‘ids’, ‘cpp11’, ‘timechange’,
    ‘systemfonts’, ‘textshaping’, ‘clipr’, ‘vroom’, ‘tzdb’, ‘progress’,
    ‘selectr’, ‘broom’, ‘conflicted’, ‘dbplyr’, ‘dplyr’, ‘dtplyr’,
    ‘forcats’, ‘ggplot2’, ‘googledrive’, ‘googlesheets4’, ‘haven’,
    ‘hms’, ‘lubridate’, ‘modelr’, ‘purrr’, ‘ragg’, ‘readr’, ‘readxl’,
    ‘reprex’, ‘rstudioapi’, ‘rvest’, ‘tidyr’, ‘xml2’

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/colorspace_2.1-1.zip’
Content type ‘application/zip’ length 2666029 bytes (2.5 MB) downloaded
2.5 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/bit_4.5.0.zip’ Content
type ‘application/zip’ length 1178435 bytes (1.1 MB) downloaded 1.1 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/farver_2.1.2.zip’
Content type ‘application/zip’ length 1519630 bytes (1.4 MB) downloaded
1.4 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/labeling_0.4.3.zip’
Content type ‘application/zip’ length 63169 bytes (61 KB) downloaded 61
KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/munsell_0.5.1.zip’
Content type ‘application/zip’ length 243912 bytes (238 KB) downloaded
238 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/RColorBrewer_1.1-3.zip’
Content type ‘application/zip’ length 54471 bytes (53 KB) downloaded 53
KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/viridisLite_0.4.2.zip’
Content type ‘application/zip’ length 1300817 bytes (1.2 MB) downloaded
1.2 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/rematch_2.0.0.zip’
Content type ‘application/zip’ length 19291 bytes (18 KB) downloaded 18
KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/bit64_4.0.5.zip’
Content type ‘application/zip’ length 504512 bytes (492 KB) downloaded
492 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/prettyunits_1.2.0.zip’
Content type ‘application/zip’ length 155478 bytes (151 KB) downloaded
151 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/backports_1.5.0.zip’
Content type ‘application/zip’ length 122682 bytes (119 KB) downloaded
119 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/generics_0.1.3.zip’
Content type ‘application/zip’ length 83692 bytes (81 KB) downloaded 81
KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/blob_1.2.4.zip’
Content type ‘application/zip’ length 49795 bytes (48 KB) downloaded 48
KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/DBI_1.2.3.zip’ Content
type ‘application/zip’ length 937674 bytes (915 KB) downloaded 915 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/tidyselect_1.2.1.zip’
Content type ‘application/zip’ length 228157 bytes (222 KB) downloaded
222 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/data.table_1.16.0.zip’
Content type ‘application/zip’ length 2476631 bytes (2.4 MB) downloaded
2.4 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/gtable_0.3.5.zip’
Content type ‘application/zip’ length 226947 bytes (221 KB) downloaded
221 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/isoband_0.2.7.zip’
Content type ‘application/zip’ length 1929381 bytes (1.8 MB) downloaded
1.8 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/scales_1.3.0.zip’
Content type ‘application/zip’ length 716055 bytes (699 KB) downloaded
699 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/gargle_1.5.2.zip’
Content type ‘application/zip’ length 805127 bytes (786 KB) downloaded
786 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/uuid_1.2-1.zip’
Content type ‘application/zip’ length 52934 bytes (51 KB) downloaded 51
KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/cellranger_1.1.0.zip’
Content type ‘application/zip’ length 106777 bytes (104 KB) downloaded
104 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/ids_1.0.1.zip’ Content
type ‘application/zip’ length 126240 bytes (123 KB) downloaded 123 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/cpp11_0.5.0.zip’
Content type ‘application/zip’ length 294289 bytes (287 KB) downloaded
287 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/timechange_0.3.0.zip’
Content type ‘application/zip’ length 513458 bytes (501 KB) downloaded
501 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/systemfonts_1.1.0.zip’
Content type ‘application/zip’ length 1337314 bytes (1.3 MB) downloaded
1.3 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/textshaping_0.4.0.zip’
Content type ‘application/zip’ length 1211754 bytes (1.2 MB) downloaded
1.2 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/clipr_0.8.0.zip’
Content type ‘application/zip’ length 55575 bytes (54 KB) downloaded 54
KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/vroom_1.6.5.zip’
Content type ‘application/zip’ length 1343099 bytes (1.3 MB) downloaded
1.3 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/tzdb_0.4.0.zip’
Content type ‘application/zip’ length 1016542 bytes (992 KB) downloaded
992 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/progress_1.2.3.zip’
Content type ‘application/zip’ length 88585 bytes (86 KB) downloaded 86
KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/selectr_0.4-2.zip’
Content type ‘application/zip’ length 486462 bytes (475 KB) downloaded
475 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/broom_1.0.6.zip’
Content type ‘application/zip’ length 1926621 bytes (1.8 MB) downloaded
1.8 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/conflicted_1.2.0.zip’
Content type ‘application/zip’ length 57536 bytes (56 KB) downloaded 56
KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/dbplyr_2.5.0.zip’
Content type ‘application/zip’ length 1262106 bytes (1.2 MB) downloaded
1.2 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/dplyr_1.1.4.zip’
Content type ‘application/zip’ length 1583186 bytes (1.5 MB) downloaded
1.5 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/dtplyr_1.3.1.zip’
Content type ‘application/zip’ length 358593 bytes (350 KB) downloaded
350 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/forcats_1.0.0.zip’
Content type ‘application/zip’ length 428118 bytes (418 KB) downloaded
418 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/ggplot2_3.5.1.zip’
Content type ‘application/zip’ length 5010342 bytes (4.8 MB) downloaded
4.8 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/googledrive_2.1.1.zip’
Content type ‘application/zip’ length 1907890 bytes (1.8 MB) downloaded
1.8 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/googlesheets4_1.1.1.zip’
Content type ‘application/zip’ length 522874 bytes (510 KB) downloaded
510 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/haven_2.5.4.zip’
Content type ‘application/zip’ length 773004 bytes (754 KB) downloaded
754 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/hms_1.1.3.zip’ Content
type ‘application/zip’ length 105628 bytes (103 KB) downloaded 103 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/lubridate_1.9.3.zip’
Content type ‘application/zip’ length 986807 bytes (963 KB) downloaded
963 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/modelr_0.1.11.zip’
Content type ‘application/zip’ length 202772 bytes (198 KB) downloaded
198 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/purrr_1.0.2.zip’
Content type ‘application/zip’ length 510675 bytes (498 KB) downloaded
498 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/ragg_1.3.3.zip’
Content type ‘application/zip’ length 1966244 bytes (1.9 MB) downloaded
1.9 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/readr_2.1.5.zip’
Content type ‘application/zip’ length 1205315 bytes (1.1 MB) downloaded
1.1 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/readxl_1.4.3.zip’
Content type ‘application/zip’ length 1204052 bytes (1.1 MB) downloaded
1.1 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/reprex_2.1.1.zip’
Content type ‘application/zip’ length 504810 bytes (492 KB) downloaded
492 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/rstudioapi_0.16.0.zip’
Content type ‘application/zip’ length 339002 bytes (331 KB) downloaded
331 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/rvest_1.0.4.zip’
Content type ‘application/zip’ length 308620 bytes (301 KB) downloaded
301 KB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/tidyr_1.3.1.zip’
Content type ‘application/zip’ length 1270628 bytes (1.2 MB) downloaded
1.2 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/xml2_1.3.6.zip’
Content type ‘application/zip’ length 1613596 bytes (1.5 MB) downloaded
1.5 MB

trying URL
‘https://cran.rstudio.com/bin/windows/contrib/4.4/tidyverse_2.0.0.zip’
Content type ‘application/zip’ length 431373 bytes (421 KB) downloaded
421 KB

package ‘colorspace’ successfully unpacked and MD5 sums checked package
‘bit’ successfully unpacked and MD5 sums checked package ‘farver’
successfully unpacked and MD5 sums checked package ‘labeling’
successfully unpacked and MD5 sums checked package ‘munsell’
successfully unpacked and MD5 sums checked package ‘RColorBrewer’
successfully unpacked and MD5 sums checked package ‘viridisLite’
successfully unpacked and MD5 sums checked package ‘rematch’
successfully unpacked and MD5 sums checked package ‘bit64’ successfully
unpacked and MD5 sums checked package ‘prettyunits’ successfully
unpacked and MD5 sums checked package ‘backports’ successfully unpacked
and MD5 sums checked package ‘generics’ successfully unpacked and MD5
sums checked package ‘blob’ successfully unpacked and MD5 sums checked
package ‘DBI’ successfully unpacked and MD5 sums checked package
‘tidyselect’ successfully unpacked and MD5 sums checked package
‘data.table’ successfully unpacked and MD5 sums checked package ‘gtable’
successfully unpacked and MD5 sums checked package ‘isoband’
successfully unpacked and MD5 sums checked package ‘scales’ successfully
unpacked and MD5 sums checked package ‘gargle’ successfully unpacked and
MD5 sums checked package ‘uuid’ successfully unpacked and MD5 sums
checked package ‘cellranger’ successfully unpacked and MD5 sums checked
package ‘ids’ successfully unpacked and MD5 sums checked package ‘cpp11’
successfully unpacked and MD5 sums checked package ‘timechange’
successfully unpacked and MD5 sums checked package ‘systemfonts’
successfully unpacked and MD5 sums checked package ‘textshaping’
successfully unpacked and MD5 sums checked package ‘clipr’ successfully
unpacked and MD5 sums checked package ‘vroom’ successfully unpacked and
MD5 sums checked package ‘tzdb’ successfully unpacked and MD5 sums
checked package ‘progress’ successfully unpacked and MD5 sums checked
package ‘selectr’ successfully unpacked and MD5 sums checked package
‘broom’ successfully unpacked and MD5 sums checked package ‘conflicted’
successfully unpacked and MD5 sums checked package ‘dbplyr’ successfully
unpacked and MD5 sums checked package ‘dplyr’ successfully unpacked and
MD5 sums checked package ‘dtplyr’ successfully unpacked and MD5 sums
checked package ‘forcats’ successfully unpacked and MD5 sums checked
package ‘ggplot2’ successfully unpacked and MD5 sums checked package
‘googledrive’ successfully unpacked and MD5 sums checked package
‘googlesheets4’ successfully unpacked and MD5 sums checked package
‘haven’ successfully unpacked and MD5 sums checked package ‘hms’
successfully unpacked and MD5 sums checked package ‘lubridate’
successfully unpacked and MD5 sums checked package ‘modelr’ successfully
unpacked and MD5 sums checked package ‘purrr’ successfully unpacked and
MD5 sums checked package ‘ragg’ successfully unpacked and MD5 sums
checked package ‘readr’ successfully unpacked and MD5 sums checked
package ‘readxl’ successfully unpacked and MD5 sums checked package
‘reprex’ successfully unpacked and MD5 sums checked package ‘rstudioapi’
successfully unpacked and MD5 sums checked package ‘rvest’ successfully
unpacked and MD5 sums checked package ‘tidyr’ successfully unpacked and
MD5 sums checked package ‘xml2’ successfully unpacked and MD5 sums
checked package ‘tidyverse’ successfully unpacked and MD5 sums checked

The downloaded binary packages are in C:\_packages \`\`\`
