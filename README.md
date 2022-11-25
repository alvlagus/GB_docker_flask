# python-flask-docker
Итоговый проект курса "Машинное обучение в бизнесе"

Стек:

ML: sklearn, pandas, numpy  
API: flask  
Данные: Размеченный датасет, состоящий из заголовков и классификатора новость вымышленная или реальная.  
В файле находится таблица, состоящая из двух колонок. В колонке title записан заголовок новости. В колонке is_fake содержатся метки: 0 – новость реальная; 1 – новость выдуманная.   
https://drive.google.com/file/d/1vsAYoiqhdhpqm-vJkixHv0OHTVm7QqPy/view?usp=share_link

Задача: требуется разработать модель, которая будет способна различать заголовки реальных и выдуманных новостей. Бинарная классификация

Используемые признаки:

- title (text)

Преобразования признаков: tfidf

Модель: logreg

### Клонируем репозиторий и создаем образ
```
$ git clone https://github.com/alvlagus/GB_docker_flask.git
$ cd GB_docker_flask_project
$ docker build -t alvlagus/gb_docker_flask_project .
```

### Запускаем контейнер

Здесь Вам нужно создать каталог локально и сохранить туда предобученную модель (<your_local_path_to_pretrained_models> нужно заменить на полный путь к этому каталогу)
```
$ docker run -d -p 8180:8180 -p 8181:8181 -v <your_local_path_to_pretrained_models>:/app/app/models alvlagus/gb_docker_flask_project
```
