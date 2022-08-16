# Разработка на PlayStation

Складываем сюда инфу по различным железкам и программам, которые применялись для официальной разработки на PlayStation.

Вот тут много инфы: http://www.lingjr.com/collection_sony_ps.htm

## Общий обзор

### PsyQ

В комплектах разработчика наблюдается порядочный бардак :smiley:

Главным инструментом для разработки был PsyQ от SN SYSTEMS. PsyQ содержал в своем составе компилятор C (CCPSX), ассемблер (ASPSX), линкер (PSYLINK) и программу для управления библиотеками (PSYLIBD).

Кроме утилит для построения программ он включал также в свой состав библиотеки написанные Sony, для взаимодействия с железом PlayStation, а также заголовочные файлы (INCLUDE), к этим библиотекам. Версий PsyQ было несколько и отличались они небольшими изменениями (исправлениями ошибок в либах).

Также в состав PsyQ входила базовая документация: Library Overview (LIBOVR) и Library Reference (LIBREF).

Версии PsyQ:
- 3.3
- 4.0
- 4.2
- 4.3
- 4.3.1
- 4.4
- 4.6: 27/JUL/1999
- 4.7: 02/FEB/2000

### Документация

Документация поставлялась на специальных дисках, либо по электронной почте. Также были конференции, где разработчикам разжевывались хитрые детали работы с железом (GTE, MDEC), потому что например та же либа для программирования GTE очень тупо написана. Неоднозначные имена функции и очень "низкоуровневая" среда. Фактически разработчикам предлагалось управлять регистрами GTE)))

Известно несколько версий дисков с документацией под кодовым обозначением `DTL-S2003`.

### Утилиты

Кроме документации также были отдельные диски с набором программ (для работы с графикой, звуком и пр.).

Известно несколько версий дисков с программами под кодовым обозначением `DTL-S2002`.

В качестве IDE предлагался CodeWarrior, но сомневаюсь что он нашёл широкое распространение. Проще всего было делать MAKE-файлами.

### Железо

Разработчикам предлагались как специальные девкиты (development kit), которые представляли собой модифицированные PlayStation, так и "запасные части", для программирования отдельных частей PSX.

Какие были девкиты и железки:

Девкиты в виде плат для компьютера, отличительная особенность - увеличенный до 8MB размер оперативки:
- DTL-H500, DTL-H505: вроде как самый первый девкит
- DTL-H2000: более новая модель, 2 платы ISA
- DTL-H2500: уже на PCI
- DTL-H2700: тоже PCI

Также были специальные "проверочные" консоли, которые были раскрашены в синий и зеленый цвета. Размер оперативки в них был такой же как и в Retail-версии консоли (2MB):
- DTL-H1000: синяя, чипы ревизии "B"
- DTL-H1100: синяя, чипы ревизии "B"
- DTL-H1200: зеленая, чипы ревизии "C"

Отличие от обычных консолей заключалось в отсутствии защиты CD от копирования.

![DTL-H1202](/wiki/imgstore/DTL-H1202.jpg)

И наконец был ещё NetYaroze: девкит для непрофессионалов, который шёл в комплекте с диском NetYaroze SDK. Про этот девкит известно достаточно много.

Все отладочные версии PSX имели специальный BIOS, нередко существенно отличающийся от "игровой" версии. Одним из существенных отличий заключается отсутствие ROM-шрифтов Kanji, которые прошиты в Retail-версии BIOS, для этого в девкитах используется специальный патч.

Отличительной особенностью также является огромное количество патчей вообще. Патчи видимо распространялись через email, потому что интернета тогда как такового не было. Видимо очень сложно было разработчикам быть уверенным, что они используют все актуальные патчи на библиотеки Sony :-)

## DTL-H700

DTL-H700 - Sound artist board. В состав комплекта входит специальная плата с оптическим выходом для Mac, на борту которой находится оригинальный чип SPU, а также программа DTL-S710 (Sound artist tool for Macintosh).

http://www.lingjr.com/images/sony_ps/ps_dtlh700_boxed.JPG

## DTL-H800

Версия Sound artist board для IBM PC.

http://www.lingjr.com/images/sony_ps/ps_dtlh800_boxed_1.JPG

## DTL-H500 / DTL-H505

Самый первый девкит:

![DTL-H500](/wiki/imgstore/DTL-H500.jpg)

Цитата с http://playstationmuseum.com/

The DTL-H505, codename MW.3, is the earliest development hardware with final PlayStation silicon and appeared in late Spring 1994. Most of these target boxes lacked sound hardware (or libraries to make use of it) and there was no CD drive. The museum is under the assumption that it utilized the CD-emulator board. Sony's next move was to consolidate the target box to a standard PC platform by way of two ISA cards (DTL-H2000) and develop an external CD-ROM drive (DTL-H2010).

Note: As you can imagine, there does exist an MW.2 which is believed to be similar to MW.3 but with beta silicon (meaning the PlayStation architecture was not finalized).

## DTL-H2000

http://www.lingjr.com/images/sony_ps/ps_dtlh2000_boxed_1.JPG

На эту модель есть документация, из которой можно понять что представляет из себя этот комплект:
- Аппаратно это чудо инженерной мысли представляет собой 2 полноразмерные платы ISA (лол), для IBM PC совместимого компьютера
- На платах находится железо, идентичное Retail консоли: центральный процессор, GPU, SPU и CD-ROM
- Оперативная память увеличена до 8MB, но также есть возможность загружать систему с ограничением в 2MB, как на реальной консоли
- Контроллеры и SIO/PIO были с измененными портами

Также в состав девкита входил внешний CD-привод DTL-H2010.

DTL-H2080 (Controller & Memory Card Adaptor)

|![DTL-H2000-CPU1_01](/wiki/imgstore/DTL-H2000-CPU1_01.jpg)|![DTL-H2000-CPU2_01](/wiki/imgstore/DTL-H2000-CPU2_01.jpg)|
|---|---|

## DTL-H2500

Вместо двух устаревших ISA используется одна плата PCI.

http://www.lingjr.com/images/sony_ps/ps_dtlh2500_boxed_1.JPG

## DTL-H2700

is a three layer development tool, it's combined with DTL-H2700 ISA I/F Board , DTL-H2700 CPU Board & DTL-H2700 ANALYZER Board.
It seems the last version of PlayStation development board for IBM/ATs, because the DTL-T10000 (PlayStation 2 Development System) also runs PlayStation development programmes.

http://www.lingjr.com/images/sony_ps/ps_dtlh2700b.JPG

Ссылки в мануалах также подтверждают, что это была последняя версия "железного" девкита для PlayStation.

## Контроллер для DTL-H2000, DTL-H2500, DTL-H2700

Оборудован обычным COM-портом.

![DTLH2000_controller](/wiki/imgstore/DTLH2000_controller.jpg)

Также существует специальный адаптер-переходник DTL-H2080, который позволяет подключать обычные контроллеры и карты памяти к девкиту.

## CD Emulator

http://www.lingjr.com/images/sony_ps/ps_dtls2020_boxed_1.JPG

DTL-S2020 - специальная плата и набор утилит для имитации реального привода. Данные хранятся на SCSI HDD.

## NetYaroze, "яроза"

![Net-Yaroze-Full-Sdk](/wiki/imgstore/Net-Yaroze-Full-Sdk.jpg)

В комплект входило:
- Консоль (2MB оперативки)
- 2 обычных контроллера
- специальный донгл в виде карты памяти
- шнурок для SIO
- печатные мануалы (DTL-S3000)
- загрузочный диск (DTL-S3030 для JAP, DTL-S3035 для EU)
- диск с NetYaroze SDK (DTL-S3040 для JAP). Вместо проприетарных компиляторов использовался GNU, а все библиотеки были перелопачены и объединены в одну - LIBPS.

Региональной защиты также не было.

Судя по всему яроза была просто перекрашенной "проверочной" версией девкита (ну и с добавленными аксессуарами). По аналогии с кодами дисков, возможно код всего девкита был DTL-H3000.

## Комплект программ разработчика

Кроме PsyQ toolchain, Sony предлагала разработчикам множество программ для редактирования графических и звуковых данных, CD-эмуляторы и прочее. Рассмотрим все известные программы.

Судя по интерфейсу, часть из них разрабатывалась ещё в Windows 3.11. Просто удивительно что они ещё запускаются в Windows 7 :smiley:

### SN Debugger

SN SYSTEMS предлагала отладчик, который включал в себя STUB для взаимодействия с отладчиком, runtime (LIBSN) для интеграции отладчика в приложение, а также DLL для управления DTL-H2500.

Интегрированная среда отладчика:

![SN_Debugger](/wiki/imgstore/SN_Debugger.jpg)

### Performance Analyzer

Достаточно крутая программа, которая базировалась на возможности семплирования сигналов шин в платах девкита. Предоставляла разработчику разнообразную статистику. Скриншоты:

|![PA_000](/wiki/imgstore/PA_000.jpg)|![PA_001](/wiki/imgstore/PA_001.jpg)|
|---|---|

### LightWave 3D

Для моделирования 3D-графики предлагалась программа LightWave 3D, версии 4.0

### Плагин для 3DS

Плагин для 3DS MAX, который мог сохранять модельки в формате RSD.

### MOVLIB 

Содержит в составе библиотеку и хедер для сжатия битстрима MDEC (MDEC Encoder), который может быть затем распакован с помощью библиотеки libpress.

То есть разработчику предлагалось самому сжимать исходные графические данные и хранить так, как он хочет.

### RSDTOOL

Текстурирование моделей RSD.

RSD это "исходный" текстовый формат 3D-моделей, которые затем компилируются утилитой RSDLINK в двоичные файлы TMD.

### TIMTOOL

TIM - это графические файлы, приспособленные для быстрой загрузки в память GPU. Особенностью TIM является специальный "палитровый" формат, который аппаратно используется GPU (CLUT). При этом индексы палитры и сама палитра (CLUT) хранятся в видеопамяти по отдельности.

Поэтому есть много утилит для конвертирования BMP в TIM, TIM-редакторы и проч.

### Утилиты для работы со звуком

Так как SPU использует специальный формат хранения данных (ADPCM), то перед использованием WAV его было необходимо конвертировать.

Формат звуковых файлов PSX : VAG. Для конвертирования применялись утилиты WAV2VAG и AIFF2VAG.

Также ещё были файлы "банков" - VAB, они применялись для создания MIDI-подобных треков, в специальной программе-трекере VABTOOL:

![VABTOOL](/wiki/imgstore/VABTOOL.jpg)

Тестировалось все это добро на специальных железках DTL-H700 (для Мака) и DTL-H800 (для PC), соответственно в VABTOOL были драйвера для этих плат.

Также была библиотека ENCVAG для конвертирования PCM в формат VAG.

### CDEMU

Вместо реального девайса SN SYSTEMS разработала эмулятор в виде специальной платы. При этом сами данные хранились на жестком диске SCSI, а для управления всей этой лабудой применял