# Установка ubuntu 16/04
запускаем виртуальную машину.Нас попросят выбрать загрузочный диск
Настройка сети.
Как я говорил выше, на гостевой системе нам нужен выход в интернет и связь с хостом. Для этого для гостевой системы у нас будет две сетевые карты. В нашем случае eth0 – для связи с хостом, а eth1 – для выхода в интернет. Выход в интернет будет через NAT. Хорошо, настраиваем.

Открываем файл /etc/network/interfaces для редактирования под рутовыми правами. Я делаю, так:

Открываю mc под рутом, команда sudo mc
Перехожу в нужный каталог
И открываю файл на редактирование F4
Редактируем файл следующим образом:


iface eth0 inet static

address 192.168.100.100

netmask 255.255.255.0

auto eth0



iface eth1 inet dhcp

auto eth1

Включаем сетевой адаптер
Тип подключения выбираем «Виртуальный адаптер хоста»
Имя выбираем «VirtualBox Host-Only Ethernet Adapter»
Все остальное оставляем без изменений
Проверяем интернет, запустим пинг


ping ya.ru

Пинг идет – интернет есть.
Проверяем интернет, запустим пинг


ping ya.ru

Пинг идет – интернет есть.
