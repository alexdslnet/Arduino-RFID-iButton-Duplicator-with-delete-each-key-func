# Arduino-RFID-iButton-Duplicator
  Доработка проекта "Копировальщик ключей для домофона RFID с OLED дисплеем и хранением 8 ключей в памяти EEPROM"  
  Автор: [МЕХАТРОН DIY, AlexMalov, 2019](https://github.com/AlexMalov/EasyKeyDublicatorRFID_OLED/)  
  Аппаратная часть построена на Arduino Nano или Arduino Pro Mini
  Две библиотеки лежат в папке с проектом остальные без проблем устанавливаюся через менеджер библиотек, для работы с модулем RC522 я использовал [ЭТУ БИБЛИОТЕКУ](https://github.com/miguelbalboa/rfid)
# Мои доработки
1. Переназначил вывод генерации 125 кГц с 11 вывода на 3 вывод чтобы освободить шину SPI;
2. Добавлена подержка работы с модулем RC522, модуль подключается по SPI шине к 11-12-13 пинам Arduino и позволяет копировать ключи Mifare Classic 1K 13.56Mhz;
3. Написаны функции чтения и записи UID в брелок типа Mifare Zero, этого как правило достаточно для нормальной работы брелка;
4. Добавил возможность принудительной очистки EEPROM, для этого перед вкл. прибора нужно зажать кнопку энкодера и неотпускать ее пока не засветится красный светодиод
5. Также в место режима blueMode я сделал режим очистки и восстановления Mifare брелка, когда метка неопределяется и нечитается пробуем этот режим. Если кому то нужен режим blueMode, то просто раскоментируйте #define BLUE_MODE в начале кода;
# Необходимые компоненты
  !Ардуину нужно брать на Atmega328P на 168-ю не влезит!  
  Arduino Nano https://alii.pub/6ms6vk   https://alii.pub/6ms6yv   https://alii.pub/6ms70f  
  Arduino ProMini https://alii.pub/6ms72y  
  RC522 модуль https://alii.pub/6ms75a   https://alii.pub/6ms7ac   https://alii.pub/6ms7bb  
  Повышающий модуль с ЗУ Li-ion https://alii.pub/6ms7f7   https://alii.pub/6ms7hc   https://alii.pub/6ms7ii  
  Плата зарядки Li-ion https://alii.pub/6ms7me   https://alii.pub/6ms7ox   https://alii.pub/6ms7r9   https://alii.pub/6ms7u6  
  Энкодер   https://alii.pub/6ms80l   https://alii.pub/6ms852   https://alii.pub/6ms89q лучше брать именно такие (прямоугольные как на схеме НЕ БРАТЬ - они плохо работают)  
  Брелки заготовки   13.5мГц https://alii.pub/6msc7a   https://alii.pub/6mscbd  125кГц  https://alii.pub/6msche  
  
  ![Схема подключения](Scheme.png)  
  
  Вид устройства в моем исполнении, корпус напечатан на 3D принтере, файл модели лежит в папке "BOX"  
  ![alt text](/BOX/Photo1.jpg)  ![alt text](/BOX/Photo3.jpg)  ![alt text](/BOX/Photo4.jpg)  
  [![Watch the video](/BOX/Photo1.jpg)](https://youtu.be/deiOaTfzMO0)
