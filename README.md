# AnalizPDFMistral
Это проект по созданию базы знаний в формате PDF, на которую будет опираться наша модель MISTRAL/ и отвечать на наши вопросы
Вообще задумку этого кода мы хотели внедрить в телеграмм бот. Но у нас это, к сожалению, не вышло. Все наши попытки оказались тщетны.
Тем не менее, в колабе, до сих пор есть код телеграмм бота. Его строчки можно просто не запускать.

Цель:
Идея проекта заключается в следующем : мы должны загрузить аудиофайл  диалога и вывести этот диалог в формате pdf, чтобы наша модель могла ее анализировать, отвечая на наши вопросы.

 Чтобы не тратить время на запуск кода также будет приложена  скриншоты ответов на pdf файл с диалогом, и мы взяли отдельный файл на 300 страниц уголовного кодекса.
 Все время обработки для диалога и для большого pdf файла я расписал в самом коде.

 #######################
 ТЕХНИЧЕСКАЯ ЧАСТЬ:
  Убедительная просьба перед запуском кода, пожалуйста, загрузите все необходимые файлы, включая шрифты, они будут в главной ветке этого репозитория. А так же создайте папку Data, ее путь /content/sample_data/Data

   В эту папку можно загрузить сразу несколько pdf файлов, это могут быть книги, статьи и те же самые диалоги, но обязательно в формате pdf. Модель будет опираться только на эти данные, если в этих данных она не найдет       
   нужного результата, модель скажет, что она не знает. 

   Главная идея - это разбить все файлы на определенные chunk_size и сделать эмбединг каждого "контейнера слов" и модель ищет среди них наиболее подходящий ответ на вопрос (сравнивая вектора).
