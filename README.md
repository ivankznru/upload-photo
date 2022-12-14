### Учебный проект для закрепления полученных знаний на курсе PHP в SkillBox

---

**Что нужно сделать:**

Реализуйте HTML-форму для файла (фотографии) на сервер. Ограничьте возможность отправки более одного файла в рамках одной сессии.

1. Реализуйте HTML-форму для файла. Для этого создайте отдельный файл send_photo.php и опишите в нём HTML-форму полем для отправки файла (input type=’file’). Метод формы — POST, action — сам файл send_photo.php. Обратите внимание, что форма должна иметь enctype "multipart/form-data".
2. После кода формы реализуйте серверную логику на PHP (отделите PHP код тегами <?php ?>. 
3. В самом начале скрипта проинициализируйте сессию (функция session_start). В сессию записывайте количество успешных загрузок файла. Если количество > 1 — выведите ошибку. Получить доступ к переменным сессии можно с помощью массива $_SESSION.
4. Реализуйте непосредственно загрузку файла. Создайте подкаталог images и копируйте загруженные файлы в него. Для копирования используйте функцию move_uploaded_files. Все операции с файлами выполняйте внутри блоков try .. catch. 
5. При загрузке файла проверьте его расширение — загружать можно только картинки форматов JPG и PNG. Также проверьте размер загружаемого файла — он не должен превышать 2 Мбайт. В ином случае выведите ошибку. 
6. Если файл загружен успешно, увеличьте на единицу счётчик количества успешных попыток загрузки, который хранится в сессии.
7. После успешной загрузки фотографии сделайте редирект на файл фотографии с помощью функции header().
