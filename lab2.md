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

Диаграмма топологии:

![Диаграмма](https://user-images.githubusercontent.com/52206303/226279954-83a2380e-be23-499d-9ce5-e39c62f837df.png)

## Часть 2

Во второй части лабораторной работы необходимо было собрать сеть по данной схеме с несколькими VLAN'ами:

![Схема](https://user-images.githubusercontent.com/52206303/226303705-dc75d9e2-fae8-4f6d-bd94-f2c3be9fc640.png)

Создал три VLAN'а: Data, Voice и Managment:

![VLANs](https://user-images.githubusercontent.com/52206303/226305846-b0bd2875-5fc2-4665-aa21-da2ed8718e0b.png)

Настроил VLAN 30:

![VLAN 30](https://user-images.githubusercontent.com/52206303/226306219-0ef23612-63e4-44af-b649-aef17d013c7e.png)

Установил маршрут по умолчанию:

![trunk](https://user-images.githubusercontent.com/52206303/226308135-94de9101-dc1e-44d9-b879-ea891e0cd6b1.png)

![vlan 10 20](https://user-images.githubusercontent.com/52206303/226309182-6be8e9ea-8528-437c-8b39-560927800e81.png)

![image](https://user-images.githubusercontent.com/52206303/226312393-9807d9bd-bd13-402a-ad72-16cfef410f3f.png)

![image](https://user-images.githubusercontent.com/52206303/226312476-0e114586-6c87-4f9a-89df-45fba7cf8a0b.png)

![image](https://user-images.githubusercontent.com/52206303/226312897-c36969f5-986e-4d05-9316-a3163aec54ae.png)

![image](https://user-images.githubusercontent.com/52206303/226313567-1696b909-28f3-4691-8166-634c6f618aec.png)

![image](https://user-images.githubusercontent.com/52206303/226314590-0926b5be-7d80-43fb-981f-948883652dcd.png)

![image](https://user-images.githubusercontent.com/52206303/226315650-bfb2ea5d-4a1b-4c1a-9954-42d9e539b7ad.png)

![DHCP на PC](https://user-images.githubusercontent.com/52206303/227766836-8e722a6b-219b-4578-8692-f6302ad59e1a.png)

![Звонок](https://user-images.githubusercontent.com/52206303/227766761-bb03eeab-dd3a-436e-9ffa-1c5cae681c0b.png)

![Пинг](https://user-images.githubusercontent.com/52206303/227767002-12f83e48-e4e2-4c90-accc-f8525b308611.png)

![Switchport 1-3](https://user-images.githubusercontent.com/52206303/227767116-9fd42a82-a19c-44d8-b47c-0adfe80827a8.png)

## Вывод
В ходе лабораторной работы я получил базовые навыки работы с IP-телефонией на базе Cisco Callmanager Express, смоделировал PC-сеть и сеть IP-телефонов. Для сети c телефонией настроил VLAN и DHCP-сервер, автоматически выдал телефонам линии и смог провести "звонок" между двумя устройствами.
