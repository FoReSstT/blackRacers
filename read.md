# РУКОВОДСТВО ПОЛЬЗОВАТЕЛЯ
BR-2G 
![Рисунок1](https://user-images.githubusercontent.com/80317959/129823910-77be7fb0-0ab2-45dd-8bca-df48c1715f8c.png)
BlackRacers 
WRO 2021
---
## Обзор репозитория
1.	3Д модели: они находятся в папке “3d models”
-	`` Knopka``: модель выложена в двух файлах(stl и itp), модель проектировалась в  Autodesk Inventor 2020
-	`` kuzov_BlackRacer``: модель выложена в двух файлах(stl и itp), модель проектировалась в  Autodesk Inventor 2020
2.	Схемы: находятся в папке “Schematic”
-	Электрическая схема представлена в файле: `` Schematic_BlackRacer.png``, схема проектировалась в программе EasyEda, файл: `` SCH_BlackRacer_team. Json``
-	 Кинетическая схема была составлена с использованием ГОСТ ‘а, файл: ``kinematic_scheme.jpg``
3.	Фотографии: находятся в папке “images”
-	Фотографии (`` Robot_…jpg `` ) показывают строение робота с разных сторон
-	Фото (`` Ours photo.jpeg ``)- официальное фото команды, а (`` ours funny photo.jpg ``)- забавное
4.	В папке “Program” находится весь код, используемый на роботе и на главном компьютере
-	`` wro.py ``-программа используемая в симуляторе для первичной настройки алгоритмов
-	`` wroracer ``-программа запускающаяся на роботе и управляющая его действиями
-	`` regulators.py ``-модуль регулятора движения робота
-	`` RoboAPI.py``-модуль коммуникации с роботом
-	`` wroracer_last_win.py `` -программа которая использовалась на региональных соревнованиях
-	`` start_robot.py ``-файл запускающийся на главном компьютере 
-	`` InetConnection.py``-файл создания сервера на Raspberry Pi
5.	Файлы в основном разделе:
-	`` wroracer``-программа запускающаяся на роботе и управляющая его действиями
-	``wroracer_last_win.py``-программа, которая использовалась на региональных соревнованиях
-	``start_robot.py``-файл запускающийся на главном компьютере 
-	`` README.md``-файли с ссылками на видео ролик на платформе YouTube(https://youtu.be/CJVz5bDU_gc) и исходником “Руководства пользователя”.
---
## Настройка программного обеспечения
Для настройки использования робота BR-2G вам понадобится установить следующее программное обеспечение:
1. Все последующие программы были протестированы и настроены под операционную систему Windows 10, и руководство также описывает установку под это систему. Если у вас установлена другая система, пожалуйста, воспользуйтесь поисковой системой Google или её аналогами для самостоятельного поиска установки программ. Если у вас нету графической оболочки система (командная строка), то установка клиентских программ может существенно отличаться от руководства. Мы настоятельно рекомендуем использовать последние сборки систем не ниже Windows 10, в ином случае, ответственность за неправильную установку или неработоспособность компонентов робота будете нести вы.

2. Программа для коммуникации с устройствами по протоколу SSH и SFTP. Например, Bitvise SSH Client, которую можно скачать с официального сайта. 
	-	Для этого перейдите по ссылке https://www.bitvise.com/ssh-client-download и нажмите кнопку «Bitvise SSH Client 		Installer».
 
	![image002](https://user-images.githubusercontent.com/80317959/129824608-fe3af042-959d-4ccf-aaa3-9312ea026d93.png)
	-	Откройте скачанный установочный файл.
 
	![image003](https://user-images.githubusercontent.com/80317959/129824636-e8de3e8c-bb1c-483a-855b-0d9d3c0097fc.png)
	-	После открытия разрешите приложению вносить изменения на устройстве. Нажмите «Да».
	-	После разрешения, у вас появятся два окна: 

	![image005](https://user-images.githubusercontent.com/80317959/129824695-265f6b38-87fe-4b9e-ade9-dca456e5ce2c.png)
	
	В маленьком окне выставьте галочку в поле «I agree to accept all the terms of the License Agreement» и нажмите «Install».
  
	![image007](https://user-images.githubusercontent.com/80317959/129825008-e49fb9a8-92bf-45db-86e1-4af12a27a9df.png)
	-	В случае успешной установки у вас появится окно, сообщающее об этом. Нажмите "OK" 
	
	![image009](https://user-images.githubusercontent.com/80317959/129825065-348fbeca-04e7-4684-9839-575cc17a7070.png)

3. Загрузить репозиторий робота с сайта GitHub.
	-	Перейдите по ссылке https://github.com/EdVenty/blackRacers/archive/refs/heads/main.zip. У вас откроется окно браузера 		 с репозиторием робота.
	-	Нажмите на зелёную кнопку «Code». 
	
	![image011](https://user-images.githubusercontent.com/80317959/129826395-4ee6dedc-dc83-436f-965b-425b9c9f78ea.png)
	-	У вас откроется следующее окно: 
		
	![image013](https://user-images.githubusercontent.com/80317959/129826444-9871a02d-922c-4320-82cf-2d65a1e288a2.png)
	
	Нажмите на кнопку «Download ZIP» для загрузки архива репозитория.
	-	Репозиторий скачается в архив в формате «.zip». 
	
	![image014](https://user-images.githubusercontent.com/80317959/129826627-684fa183-e1f1-48c9-8475-d2be2f3f2759.png)
	-	Если у вас не установлен «WinRar» или другие архиваторы, то у вас откроется следующие окно проводника: 
	
	![image016](https://user-images.githubusercontent.com/80317959/129985270-b3985063-01fc-4f07-a192-b956ab9d7fde.png)
	-	Скопируйте единственную корневую папку и извлеките в любую другую папку на вашем диске.
	
	![image018](https://user-images.githubusercontent.com/80317959/129985324-43f1e20e-9be0-4e70-a4d2-710ae2fcd5f5.png)
	![image018](https://user-images.githubusercontent.com/80317959/129985341-140a5d90-bbbe-4e24-b57b-8a1d6e348ace.png)
	-	Репозиторий загружен на ваш компьютер.
4. Программа для коммуникации с роботом по протоколу UART, для загрузки прошивки в микроконтроллер PyBoard, напрмер, «PuTTY».
	-	Перейдите по ссылке https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html. У вас откроется окно загрузки установщика PuTTY. Найдите следующую область 			(надписи могут отличаться):  
	
	![image022](https://user-images.githubusercontent.com/80317959/129985851-20ef1c04-061d-4afa-99b1-0106ab5dd788.png)
	-	Нажмите на ссылку, справа от поля «64-bit x86», если у вас система 64 бита, иначе – «32-		bit x86». У вас должен скачаться следующий файл: 

	![image024](https://user-images.githubusercontent.com/80317959/129986069-605bf70e-d59b-412b-8215-d9bc005b6f69.png)
	-	Откройте его
	
	![image026](https://user-images.githubusercontent.com/80317959/129986296-8776bb72-eb84-4783-977d-6702f69d060e.png)
	-	Нажмите кнопку «Next», и у вас откроется следующее окно: 
	
	![image028](https://user-images.githubusercontent.com/80317959/129986393-d8244a64-5e56-44aa-b48e-	04e0fd78c932.png)