University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [IP-Telephony](https://itmo-ict-faculty.github.io/ip-telephony)

Year: 2022/2023

Group: K34212

Author: Gavrilushkin Alexandr Alekseevich

Lab: Построение сети ip-телефонии между удаленными маршрутизаторами

Date of create: 26.03.2023

Date of finished: 26.03.2023

## Часть 1

Цель работы: Изучить построение сети IP-телефонии между удаленными филиалами с помощью маршрутизаторов Cisco 2811 и коммутаторов Cisco 2950Т.

Результатом лабораторной работы должна стать схема сети, представленная на рисунке ниже:

![image](https://user-images.githubusercontent.com/52206303/227784542-2a75254f-512e-4a07-85e8-4f39d9b59606.png)

Между маршрутизаторами должно быть проложено DCE/DTE соединение. Для этого я добавил роутерам необходимые разъемы:

![доп порты](https://user-images.githubusercontent.com/52206303/227785491-98327cde-4bdb-45ec-b29e-6708ecc1b4af.png)

Построил топологию:

![Топология](https://user-images.githubusercontent.com/52206303/227785646-f86a0fa2-300f-4e68-852d-cdb96cfdef2b.png)

Назначил портам роутеров, выходящих на коммутатор IP-адреса. Выбрал сети 192.168.1.0 и 172.16.1.0:

![IP router 0](https://user-images.githubusercontent.com/52206303/227785904-dff87930-a176-42d3-a678-130f3a8542af.png)

![IP router 1](https://user-images.githubusercontent.com/52206303/227785958-31abc9d3-0940-479b-936e-58661b9d603a.png)

Настроил DCE (Router 0) и DTE (Router 1) порты:

![DCE router](https://user-images.githubusercontent.com/52206303/227786754-d460239a-d996-4f01-8c55-e4a93d467c86.png)

![DTE router](https://user-images.githubusercontent.com/52206303/227786697-5793987e-805d-43f8-8d82-cef322a81c5f.png)

Настроил DHCP на каждом роутере:

![DHCP 0](https://user-images.githubusercontent.com/52206303/227786999-21b285d3-80eb-47b0-b37a-b248ae376902.png)

![DHCP 1](https://user-images.githubusercontent.com/52206303/227787022-407d5830-57fa-4c68-bba5-c14a5f3aa31b.png)

Включил VLAN на роутере и коммутаторе, настроил порты на коммутаторе:

![Switch 1 access mode](https://user-images.githubusercontent.com/52206303/227788061-30c53895-cc10-4fa5-917f-2392c1e7323f.png)

Настроил телефонию в первой сети. Установил номера 101, 102, 103:

![Telephony 0](https://user-images.githubusercontent.com/52206303/227788607-b03fe697-6431-411b-b293-19c55279ff9a.png)

Портестировал работу сервиса:

![T0 test](https://user-images.githubusercontent.com/52206303/227788654-86a2c567-3d6f-4adc-a9fe-adfe0abffe89.png)

Повторил настройку коммутатора и сервиса IP-телефонии во второй сети. Установил номера 201, 202, 203.

Настроил на обоих роутерах RIP:

![RIP](https://user-images.githubusercontent.com/52206303/227789016-c99a0134-0c24-4987-a9ba-5441422e593e.png)

Проверил работу протокола, отправив пинг между компьютерами из разных сетей:

![PING](https://user-images.githubusercontent.com/52206303/227789136-b5be3a28-44c6-430c-b955-b997d1bbea29.png)

Настроил соединение между двумя сетями IP-телефонии:

![dial peer 0](https://user-images.githubusercontent.com/52206303/227789251-c60701ac-6235-439d-b095-69b4c3378cdf.png)

![dial peer 1](https://user-images.githubusercontent.com/52206303/227789308-6e62c979-7cfd-4806-a452-d31fd18c3ea0.png)

Проверил работу сети, позвонив с номера 102 на номер 202:

![Call](https://user-images.githubusercontent.com/52206303/227789352-43b5c6cc-bf16-4831-978a-c36c9e27b0a4.png)

Звонок прошел успешно, значит, сеть настроена верно.

Диаграмма сети:

![image](https://user-images.githubusercontent.com/52206303/227790995-881e8c5c-1bcd-4293-bd59-5716256dcdeb.png)

## Вывод
В ходе лабораторной работы я научился соединять две сети с IP-телефонией, настроил динамическую маршрутизацию между двумя сетями по протоколу RIP и соединил две сети IP-телефонии с помощью сервиса dial-peer.
