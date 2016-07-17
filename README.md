# CLUNET 2.0
**CLUNET 2.0** основан на [оригинальном протоколе](https://github.com/ClusterM/clunet) **Алексея Авдюхина** _aka_ **Cluster**.
### Основные отличия
Сэмплирование ввиду затратности использования процессора микроконтроллера не использовалось, вместо этого чтение производится как в оригинале по внешним прерываниям, которые вызываются гораздо реже, чем бы при сэмплировании.
Бит приоритетов теперь 3 (в оригинале 2) что позволяет использовать 8 уровней приоретизации, биты данных передаются от старшего к младшему (в оригинале наоборот от младшего к старшему). Тем самым добавляется дополнительный арбитраж на шине, используя адрес источника, адрес назначения и т.д. То есть пр одинаковых приоритетах шину захватит устройство с бОльшим адресом.
## Схемотехника
Шина **CLUNET 2.0** использует для передачи и приема данных _**всего один**_ провод и _**одну ногу**_ микроконтроллера. Организовать и подключиться к ней возможно 2 способами:
 1. Используя любой биополярный транзистор **PNP**-типа _**(рекомендуется)**_
![Рекомендуемая схема подключения](schematic/recommended.png)
 2. Прямое простое подключение.
![Простая схема подключения](schematic/simple.png)
