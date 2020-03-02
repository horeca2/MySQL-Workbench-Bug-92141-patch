# MySQL-Workbench-Bug-92141-patch
Патч Bug #92141

Патч бага https://bugs.mysql.com/bug.php?id=92141

# Суть проблемы:
В некоторых случаях не отображаются значки первичных\внешних ключей в ER редакторе

Обнаружено, что в папке images некоторые файлы png иконок имеют очень большой размер.
В частности для рассматриваемого бага файл db.Column.pkfk.11x11.png имеет размер более 4000 байт (и это для иконки 11 х 11)
Если сжать этот файл, то проблема решится

Кроме этого файла в папке images есть и другие файлы с большим размером.
Сожмем их все c помощью advpng из https://sourceforge.net/projects/advancemame/files/advancecomp/1.15/.

Для этого:

1. Закроем MySQL Workbench
2. Скопируем файлы advpng.exe, patch.bat,	zlib.dll в папку images, у меня она в "C:\Program Files\MySQL\MySQL Workbench 8.0 CE\images"
3. Запустим patch.bat
4. Откроем MySQL Workbench

Проверено для версии 8.0.19 windows
