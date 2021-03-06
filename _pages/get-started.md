---
title: "Начало" #
lang: ru
permalink: /get-started.html
author_profile: true
---

{% include toc title="Разделы" %}

Следующие шаги подготовят вашу SD-карту к установке кастомной прошивки Coldboot Haxchi

Прежде всего, нужно убедиться, что прошивка вашей приставки 5.5.0-{% include /vars/sys_version.txt %}. Если ваша приставка на старой версии системного ПО - обновите её через настройки. 

Рекомендуется использовать SD-карту не менее 16 или 32Гб, иначе вам не хватит места для установки игр. Если вы хотите сделать резервную копию вашей Wii U на случай брика, вам нужна SD-карта как минимум в два раза больше, чем размер внутренней памяти вашей приставки (минимум 16Гб для 8-ми ГБ Wii U; минимум 64Гб для 32-х Гб Wii U).

SD-карта должна быть отформатирована в FAT32 (с кластером в 64КБ или 32 КБ). Большинство SD-карт изначально так и отформатированы.

Если вы планируете форматировать SD-карту в Windows, не используйте встроенную утилиту для форматирования, это в дальнейшем может вызывать проблемы. Лучше воспользуйтесь [`guiformat`](http://www.ridgecrop.demon.co.uk/guiformat.exe). Установите "Allocation Unit Size" в "64kb".

**Нельзя** называть SD-карту `wiiu`, это приведет к проблемам.

Прежде чем начать, рекомендуется проверить свою SD-карту на ошибки с помощью [H2testw (Windows)](h2testw-windows), [F3 (Linux)](f3-linux), или [F3X (Mac)](f3x-mac)!

## Что понадобится

* Свежая версия [WiiUSDFiles](https://github.com/rashevskyv/wiiu/releases/latest){:target="_blank"}

## Инструкция

### Часть I - Подготовительные работы

1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Скопируйте _содержимое_ `.zip-архива` [WiiUSDFiles](https://github.com/rashevskyv/wiiu/releases/latest){:target="_blank"} в корень вашей SD-карты
1. Вставьте SD-карту обратно в консоль

	Карту нужно вставлять в переднюю панель приставки. Не пытайтесь вставить её через USB-переходник в USB-порт!
	{: .notice--warning}

	Вы не увидите никаких сообщений на приставке, после того, как вставите в неё карту. Не ждите, что приставка вам напишет о том, что карта принята, или ещё чего-либо похожего.
	{: .notice--warning}

1. Включите консоль

### Часть II - Игры DS Virtual Console

Существует два метода использования кастомной прошивки Wii U.

Первый метод подразумевает запуск через браузер приставки эксплойта, который патчит систему. К сожалению, это придется делать после каждого перезапуска приставки. Кроме того, эксплойт совместимый с {% include /vars/sys_version.txt %} очень нестабилен и запускается далеко не с первого раза.

Второй метод потребует покупки недорогой игры от DS Virtual Console, через которую будет автоматически запускаться кастомная прошивка при запуске приставки. Этот метод рекомендован для большинства пользователей. Пользователи прошивки 5.5.2-{% include /vars/sys_version.txt %}, из-за нестабильности способа запуска прошивки из браузера, должны использовать только этот метод.

Игра для DS Virtual Console должна быть **законно приобретённой** и установленной во **внутреннюю память** приставки. **Не** устанавливайте игру от DS virtual console на USB-носитель.
{: .notice--warning}

Если вы планируете использовать метод с игрой DS Virtual Console, то купите её прежде чем переходить к следующей части.
{: .notice--primary}

#### Список совместимый DS Virtual Console игр

| Игры, совместимые с Haxchi|
| ------------- |
| Animal Crossing: Wild World |
| Big Brain Academy |
| Brain Age |
| DK: Jungle Climber |
| Dr. Kawashima's Brain Training |
| Kirby: Canvas Curse |
| Kirby: Mass Attack|
| Kirby: Squeak Squad / Kirby: Mouse Attack |
| Legend of Zelda: Phantom Hourglass |
| Legend of Zelda: Spirit Tracks |
| Mario & Luigi: Partners in Time |
| Mario Kart DS |
| New Super Mario Bros. |
| Pokemon Mystery Dungeon: Explorers of the Sky |
| Pokemon Ranger |
| Pokemon Ranger: Guardian Signs | 
| Pokemon Ranger: Shadows of Almia |
| Starfox Command |
| Super Mario 64 DS |
| Wario: Master of Disguise |
| WarioWare: Touched |
| Yoshi's Island DS |
| Yoshi's Touch & Go |

Для того, чтобы войти в eShop на прошивках ниже, чем {% include /vars/sys_version.txt %}, вам понадобится запустить [Homebrew Launcher](get-started#часть-iv---homebrew-launcher){:target="_blank"} и из него запустить NNU-Patcher, и только после этого вы сможете войти в eShop и купить игру, либо, если не помогло, обновиться до {% include /vars/sys_version.txt %} через настройки приставки.
{: .notice--warning}

1. Запустите eShop
	+ Если при запуске у вас возникает ошибка 105-5602
		+ Зайдите в Системные настройки, Информация о консоли, Выбор страны проживания и измените страну на "Германия", подтвердите выбор нажатием кнопки "Изменить"
		+ Перезагрузите приставку 
		+ Запустите eShop (снова будет ошибка)
		+ Зайдите в Системные настройки, Информация о консоли, Выбор страны проживания и измените страну на ту, что была до этого, подтвердите выбор нажатием кнопки "Изменить"
		+ Перезагрузите приставку 
		+ Запустите eShop, теперь он должен работать
+ Если у вас уже есть купленная установленная копия Brain Age / Brain Trainin на приставке, удалите ее и переустановите из eShop. Старые версии игры не совместимы с эксплойтом.

### Часть III - Блокировка обновления системы с помощью DNS

Обратите внимание, что если вы не заблокируете обновления этим методом на текущем и всех будущих интернет-соединениях, то все обновления для WiiU будут скачиваться и устанавливаться *автоматически* без вашего ведома и *не могут* быть отменены. 
{: .notice--danger}

Помните, что для доступа к eShop с установленными DNS, вам необходимо сначала запустить NNU-Patcher из [Homebrew Launcher](get-started#часть-iv---homebrew-launcher){:target="_blank"} (NNU-Patcher - временный патч и его нужно запускать каждый раз после перезагрузки, если вам нужен доступ к eShop).
{: .notice--info}

1. Перейдите в **Системные настройки** (System Settings), **Интернет** (Internet), **Подключиться к Интернету** (Connect to the Internet), нажмите (X) для того, чтобы отобразить имеющиеся подключения
1. Для каждого из имеющихся подключений (и для всех созданных в будущем), проделайте нижеследующие инструкции
  + Выберите "**Изменить настройки**" (Change Settings)
  + Перейдите на вторую страницу и выберите "**DNS**"
  + В пункте меню DNS выберите "**Не получать автоматически**" (Don't Auto-Obtain)
  + Введите указанные ниже адреса DNS
	  + `168.235.092.108`
	  + `081.004.127.020`
  + Нажмите "**Подтвердить**" (Confirm), а затем (B), чтобы сохранить внесенные изменения
  + Эти сервера заблокируют получение обновлений SysNAND на Wii U

### Часть IV - Homebrew launcher

Homebrew Launcher - приложение, выводящее в виде списка и позволяющее запускать другие хомбрю приложения прямо с SD-карты.

Поскольку мы запускаем его из встроенного браузера Wii U, нам понадобится доступ в интернет на консоли.

1. Запустите браузер на приставке
1. Перейдите в настройки браузера и выберите пункт "Сброс данных сохранения" (Reset Save Data)
	+ Это поможет избежать проблем при использовании уязвимости браузера
	+ Это приведёт также к удалению всех сохраненных данные, включая настройки, историю и закладки
1. Вернитесь к браузеру
1. Перейдите на сайт `u.wiidb.de`
1. Нажмите на "**HAXX**"
1. Консоль должна загрузиться в Homebrew Launcher
	* Если приставка зависла - перегрузите её, удерживая кнопку питания и пробуйте заново
	* Может понадобится ни одна попытка. Пробуйте пока не выйдет! 

___

## Выберите прошивку

[Haxchi](haxchi) (**рекомендуется**)
{: .notice--success}

Этот метод использует недорогую игру от DS Virtual Console, через которую будет запускаться кастомная прошивка при запуске приставки. Рекомендуется использовать этот метод, несмотря на то, что он требует небольших денежных вложений. Mocha CFW заброшена и давно не развивается, используйте её только, если вы очень жадный. *Рекомендуемый* метод для пользователей приставок с прошивкой {% include /vars/sys_version.txt %}, поскольку веб-эксплойт из предыдущего метода крайне нестабилен. Так же только используя Haxchi вы сможете сделать запуск эксплойта автоматически, с помощью CBHC.

___

[Mocha CFW](mocha-cfw)
{: .notice--success}

Этот метод подразумевает запуск эксплойта по новой после каждой перезагрузки приставки. Не рекомендутся использовать, поскольку Mocha CFW заброшена и давно не развивается, используйте её только, если вы очень жадный.  Крайне не рекомендуется пользоваться этим методом на прошивке {% include /vars/sys_version.txt %}, поскольку веб-эксплойт крайне нестабилен. 