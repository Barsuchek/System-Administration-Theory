# Модель OSI
Эта модель состоит из 7 уровней и полностью описывает как работают сетевые устройства.

## Что это такое?
Процесс передачи данных которые разделили на 7 частей, каждая из которых отвечает за выполнение определенной функции.

Начнем с нижнего уровня.

1. **Физический уровень**
	Передача физических сигналов(токов, света или радио) от источника к получателю.
	
	На этом уровне мы оперируем кабелями, контактами в разъемах, кодированием единиц и нулей, модуляцией сигнала и т.д
	
	Проще говоря, это уровень проводов. Самый основной стандарт на этом уровне - Ethernet, который описывает как сигналы должны кодироваться, передаваться по проводам и т.д
	
	А так же на этом уровне присутствует Bluetooth, Wi-Fi и ИК-порт.
	
	Сетевые устройства первого уровня - концентраторы и репиторы.

2. **Канальный уровень**
	Проверка и исправление ошибок передачи.
	
	**Frame(кадр)** - полезные данные к которым добавлена дополнительная служебная информация. Например адрес отправителя и получателя(MAC).
	
	**MAC** - это адрес устройства на канальном уровне.
	
	Сетевые устройства второго уровня - коммутаторы, мосты и Ethernet.
	
	Также на этом уровне находятся протоколы CDP, PPP, MPLS и другие.

3. **Сетевой уровень**
	На этом уровне происходит маршрутизация трафика.
	
	Пакет - при передаче данных на конверте отправителя и получателя указаны MAC-адреса. Внутри этого конверта находится еще один конверт, на котором указаны адреса сетевого уровня(IP).
	
	**Инкапсуляция** - процесс передачи данных с верхнего уровня на нижний.
	
	**Декапсуляция** - процесс передачи данных с нижнего уровня на верхний.
	
	Данные приходящие с верхних уровней, на каждых последующих уровнях кладутся в конверт с полезной информацией, когда устройство или приложение этого уровня получает конверт, оно знает что с ним делать благодаря этой информации.
	
	На этом уровне благодаря протоколу ICMP мы используем утилиту PING, которая помогает нам определить наличие проблем в сети.
	
	Сетевые устройства третьего уровня - маршрутизатор и все его протоколы маршрутизации.

4. Транспортный уровень
	Обеспечивает передачу данных по сети. Предназначен для надежной передачи данных от отправителя к получателю.
	
	* TCP - используется если трафик чувствителен к потерям(пакеты нельзя терять). Он обеспечивает контроль за передачей данных. Чтобы мы получили письмо по почте без изменений.
	
	* UDP - используется если трафик не чувствителен к потерям(пакеты можно терять). Например при просмотре видео пару пакетов могло потеряться, будут небольшие артефакты, но не критично.

5. Сеансовый уровень
	Управляет соединениями(сессиями), он их разрывает.
	
	Например видеоконференция, так как именно на этом уровне устанавливается каким кодеком будет кодироваться сигнал, при этом этот кодек должен присутствовать у обоих пользователей.

6. Уровень представления
	Преобразование форматов сообщений, такое как кодирование или сжатие(JPEG, GIF).
	
	Когда вы отсылаете кому-то фотку своего кота, она приходит в виде нулей и единиц, на этом уровне она преобразуется в нужный формат, который можно будет открыть.

7. Уровень приложений
	Сетевые службы которые позволяют пользователям блуждать по просторам интернета.
	
	Например TELNET, LPD, HTTP, HTTPS, DNS, DHCP, SNMP, FTP и другие.
