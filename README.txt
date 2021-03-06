Counter_downloads – счетчик скачивания файлов.

Скрипт подсчитывает количество скачиваний файлов со страницы сайта. Информация сохраняется в формате JSON (название скачиваемого файла и количество скачиваний).

В строке
<a class="MxDownload" data-nameplugin="MxBox" href="downloads/MxBox.zip" download>Скачать</a>, 
data-nameplugin="MxBox" – является указателем названия файла (вписывается вручную).

В результате, после клика по ссылке, в файле JSON информация выглядит примерно так:
{"MxBox":{"countDownloads":1}}

При добавлении скрипта на новую страницу, необходимо заменить имя файла и путь к нему.
<a class="MxDownload" data-nameplugin="MxBox_1" href="downloads/MxBox_1.zip" download>Скачать</a>

В результате строка в файле JSON, после скачивания, будет примерно такой:
{"MxBox":{"countDownloads":1},"MxBox_1":{"countDownloads":1}}

Скрипт проверяет файл JSON на предмет наличия имени файла. Если имя файла есть, количество скачиваний увеличивается на единицу, если нет – создается новый объект с именем указаным в "data-nameplugin" и количеством скачиваний 1.

Важно!
В начале работы файл JSON должен иметь пустой объект, то есть строку {}