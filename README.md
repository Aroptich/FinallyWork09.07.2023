# Информация о проекте
Необходимо организовать систему учета для питомника, в котором живут домашние и вьючные животные.
# Задание
1. Используя команду cat в терминале операционной системы Linux, создать два файла Домашние животные (заполнив файл собаками, кошками, хомяками) и Вьючные животными заполнив файл Лошадьми, верблюдами и ослы), а затем объединить их. Просмотреть содержимое созданного файла. Переименовать файл, дав ему новое имя (Друзья человека).
![Cat_Linux](https://github.com/Aroptich/FinallyWork09.07.2023/blob/main/Cat_Lunyx.png)
2.  Создать директорию, переместить файл туда.
   ![Mv_Linux](https://github.com/Aroptich/FinallyWork09.07.2023/blob/main/Mv_Lunyx.png)
3. Подключить дополнительный репозиторий MySQL. Установить любой пакет из этого репозитория.
   ![apt_mysql](https://github.com/Aroptich/FinallyWork09.07.2023/blob/main/apt_mysql.png)
   ![upt_mysql](https://github.com/Aroptich/FinallyWork09.07.2023/blob/main/upt_mysql.png)
4. Установить и удалить deb-пакет с помощью dpkg.
   ![dpkg_mysql](https://github.com/Aroptich/FinallyWork09.07.2023/blob/main/dpkg.png)
5. Выложить [историю команд](https://github.com/Aroptich/FinallyWork09.07.2023/blob/main/HistoryOfCommands.md) в терминале ubuntu
6. Нарисовать диаграмму, в которой есть класс родительский класс, домашние животные и вьючные животные, в составы которых в случае домашних животных войдут классы: собаки, кошки, хомяки, а в класс вьючные животные войдут: Лошади, верблюды и ослы).
   ![Diagram](https://github.com/Aroptich/FinallyWork09.07.2023/blob/main/Diagram.PNG)
7. В подключенном MySQL репозитории создать базу данных “Друзья человека”
   
   `CREATE DATABASE Human_friends;`
8. Создать таблицы с иерархией из диаграммы в БД

   `USE Human_friends;
CREATE TABLE animal_classes
(
	Id INT AUTO_INCREMENT PRIMARY KEY, 
	Class_name VARCHAR(20)
);

INSERT INTO animal_classes (Class_name)
VALUES ('вьючные'),
('домашние');  


CREATE TABLE packed_animals
(
	  Id INT AUTO_INCREMENT PRIMARY KEY,
    Genus_name VARCHAR (20),
    Class_id INT,
    FOREIGN KEY (Class_id) REFERENCES animal_classes (Id) ON DELETE CASCADE ON UPDATE CASCADE
);

INSERT INTO packed_animals (Genus_name, Class_id)
VALUES ('Лошади', 1),
('Ослы', 1),  
('Верблюды', 1); 
    
CREATE TABLE home_animals
(
	  Id INT AUTO_INCREMENT PRIMARY KEY,
    Genus_name VARCHAR (20),
    Class_id INT,
    FOREIGN KEY (Class_id) REFERENCES animal_classes (Id) ON DELETE CASCADE ON UPDATE CASCADE
);

INSERT INTO home_animals (Genus_name, Class_id)
VALUES ('Кошки', 2),
('Собаки', 2),  
('Хомяки', 2); 

CREATE TABLE cats 
(       
    Id INT AUTO_INCREMENT PRIMARY KEY, 
    Name VARCHAR(20), 
    Birthday DATE,
    Commands VARCHAR(50),
    Genus_id int,
    Foreign KEY (Genus_id) REFERENCES home_animals (Id) ON DELETE CASCADE ON UPDATE CASCADE
);`
