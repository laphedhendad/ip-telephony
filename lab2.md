University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [IP-Telephony](https://itmo-ict-faculty.github.io/ip-telephony)

Year: 2022/2023

Group: K34212

Author: Gavrilushkin Alexandr Alekseevich

Lab: Конфигурация voip в среде Сisco packet tracer

Date of create: 19.03.2023

Date of finished: 19.03.2023

## Часть 1

В первой части лабораторной работы необходимо было собрать сеть из 3 IP-телефонов. Целевая схема изображена на рисунке ниже:

![Схема](https://user-images.githubusercontent.com/52206303/226268848-80e03738-84c9-4c5f-a60f-0c3f2d5fe3fd.png)

Перед началом работы подключил телефоны к сети через интерфейс:

![Power On](https://user-images.githubusercontent.com/52206303/226189344-710dbd3f-c989-46e0-a6fa-db447f0237a8.png)

Собрал в Cisco Packet Tracer модель, соответствующую схеме:

![Модель](https://user-images.githubusercontent.com/52206303/226270121-f0ade174-c518-4d43-802d-11b5a81a4f39.png)

Через CLI роутера включил порт, к которому подключен коммутатор:

![Порт](https://user-images.githubusercontent.com/52206303/226270590-617f21a3-7c88-4e9e-b3ed-9ec840f6153d.png)

Изменил имя маршрутизатора:

![Rename](https://user-images.githubusercontent.com/52206303/226270785-0dce7bdf-9f82-4633-81ef-a35d60a7819f.png)

Отключил синтаксис ввода слов от DNS серверов:

![image](https://user-images.githubusercontent.com/52206303/226270943-12e35d3d-8993-4d5f-8851-d363a548db02.png)

Задал пароли для защиты маршрутизатора в удаленном режиме и режиме консоли. Команда line vty 0 1 настраивает подключение только для двух одновременных клиентов:

![Пароли](https://user-images.githubusercontent.com/52206303/226271774-5e0d2ca7-2940-4047-81c5-f5327f2916f5.png)

Назначил интерфейсу маршрутизатора IP-адрес:

![IP](https://user-images.githubusercontent.com/52206303/226272382-895d66ab-9f81-42da-a060-7f7512b72383.png)

Настроил DHCP-сервер:

![DHCP](https://user-images.githubusercontent.com/52206303/226273433-347cc1a9-f31d-4947-8cb2-2308d5d45ebb.png)

Включил VLAN-порты на маршрутизаторе и коммутаторе:

![VLANR](https://user-images.githubusercontent.com/52206303/226274338-b526496c-fb3c-4c86-bfdf-05150012d04e.png)

![VLANS](https://user-images.githubusercontent.com/52206303/226274530-aa414c09-3428-4d18-9e0b-f16de5f7d8ed.png)

Назначил диапазон VLAN портов на коммутаторе:

![VLANP](https://user-images.githubusercontent.com/52206303/226274944-6c1c489a-83be-4835-b566-f84eff11b9c7.png)

Настроил сервис телефонии на роутере. Установил количество линий и телефонов равное 3, назначил линиям номера:

![Telephony](https://user-images.githubusercontent.com/52206303/226275982-c6aea148-b6f3-4936-8e30-c0aa975f33b3.png)

Проверил работу сети, позвонив с номера 11111 на номер 22222:

![Проверка](https://user-images.githubusercontent.com/52206303/226277264-af2c463f-8a89-4271-b470-3d04d565dfab.png)

## Часть 2

Во второй части лабораторной работы необходимо было настроить IP-телефонию в простой топологии из двух IP-телефонов, коммутатора и роутера с поддержкой Cisco CallManager Express (CME). Схема сети представлена на рисунке ниже:

![Схема](https://user-images.githubusercontent.com/52206303/226194801-8d2429a6-d1fd-43f1-b1ec-6a96496e630d.png)

Чтобы изменять конфигурации устройст через терминал, необходимо зайти в привелигерованный режим:
```
Router>enable
Router#config terminal
```

Теперь изменим имя роутера на CMERouter:

![CMERouter](https://user-images.githubusercontent.com/52206303/226183042-9f66b321-4995-436f-b3c2-94df677862f4.png)

Назначим интерфейсу, к которому подсоединен коммутатор, IP-адрес 192.168.1.1:

![Router Interface](https://user-images.githubusercontent.com/52206303/226183269-757ffa99-2dc7-4215-ba6c-3322ef237172.png)

Настроим DHCP-сервер для автоматической настройки телефонов. Для этого создаем пул с TELEPHONY, назначаем ему сеть 192.168.1.0 и дефолтный роутер, который мы настроили в предыдущем пункте. При передаче голоса необходимо включить на DHCP опцию 150, чтобы телефоны импортировали настройки с TFTP (Trivial File Transfer Protocol):

![DHCP](https://user-images.githubusercontent.com/52206303/226183436-1080cb51-1ad9-4811-84f2-fa271bbf4971.png)

Устанавливаем максимальное количество номеров и телефонов, указываем адрес голосового шлюза и настраиваем автоматическое назначение линий:

![Телефония](https://user-images.githubusercontent.com/52206303/226198806-a169e4b1-e586-4f1c-9927-306c83428f7d.png)

Назначаем портам коммутатора VLAN:

![Switch](https://user-images.githubusercontent.com/52206303/226185431-3541ee4d-1883-4630-92a4-bf14fc533823.png)

Включаем все VLAN интерфейсы на коммутаторе и маршрутизаторе:
```
interface vlan1
no shutdown
```
Проверим настройки отправив пинг с роутера на оба телефона:

![Пинги](https://user-images.githubusercontent.com/52206303/226195067-9ffca045-838e-4703-a32d-77095acf734a.png)

Пинги проходят, значит, сеть настроена корректно. Попробуем совершить "звонок":

![Звонок](https://user-images.githubusercontent.com/52206303/226193811-9bbc4584-ccd8-4b84-b078-04332e41abcf.png)

Звонок проходит успешно, можно послать короткое звуковое сообщение с одного телефона на другой. Протестировать работу перевода звонков, перехвата не предоставляется возможным, так как роутер не поддерживает эти функции.

Диаграмма получившейся сети представлена на рисунке ниже:

![Схема](https://user-images.githubusercontent.com/52206303/226196498-5caac890-59af-4a45-9cab-c994e4a3afd0.png)

## Вывод
В ходе лабораторной работы я получил базовые навыки работы с IP-телефонией на базе Cisco Callmanager Express, смоделировал PC-сеть и сеть IP-телефонов. Для сети c телефонией настроил VLAN и DHCP-сервер, автоматически выдал телефонам линии и смог провести "звонок" между двумя устройствами.
