## 🔄 Перемещение и копирование файлов

### 📂 Перемещение (mv)
- mv file1.txt folder/ – переместить file1.txt в папку folder
- mv oldname.txt newname.txt – переименовать файл
- mv folder1 folder2 – переместить folder1 внутрь folder2

### 📑 Копирование (cp)
- cp file.txt backup.txt – создать копию файла
- cp -r folder1 folder2 – скопировать всю папку folder1 в folder2# Шпаргалка по Linux-командам

## 📂 Навигация по папкам
- pwd – показать текущую директорию
- ls – показать файлы в папке
- cd folder_name – перейти в папку
- cd .. – подняться на уровень выше
- mkdir new_folder – создать папку

## 📝 Работа с файлами
- touch file.txt – создать файл
- rm file.txt – удалить файл
- mv file.txt new_folder/ – переместить файл
- cp file.txt backup.txt – скопировать файл
# 📌 1️⃣ Просмотр прав доступа
ls -l  # Показать права доступа к файлам и папкам
ls -la  # Показать все файлы, включая скрытые
stat myfile.txt  # Подробная информация о файле (включая права и владельца)

# 📌 2️⃣ Изменение прав доступа (chmod)
chmod u+rwx myfile.txt  # Дать владельцу (u) право читать (r), писать (w) и выполнять (x)
chmod g-w myfile.txt  # Убрать у группы (g) право на запись (-w)
chmod o+r myfile.txt  # Дать всем остальным (o) право на чтение (+r)
chmod 777 myfile.txt  # Полные права для всех (владелец, группа, остальные)
chmod 644 myfile.txt  # Владелец: читать/писать, остальные: только читать
chmod 755 myscript.sh  # Владелец: полный доступ, остальные: могут только запускать

# 📌 3️⃣ Изменение владельца (chown)
chown newuser myfile.txt  # Назначить владельцем пользователя newuser
chown newuser:newgroup myfile.txt  # Изменить владельца и группу
sudo chown -R newuser:newgroup myfolder/  # Изменить владельца и группу для всей папки

# 📌 4️⃣ Изменение группы (chgrp)
chgrp users myfile.txt  # Назначить файл группе users

# 📌 5️⃣ Работа с sudo (администраторские права)
sudo whoami  # Проверить, есть ли у тебя root-доступ (выдаст "root" при наличии)
sudo chmod 700 /etc/shadow  # Дать доступ к важному системному файлу только root
sudo usermod -aG sudo newuser  # Добавить пользователя в sudo-группу

# 📌 6️⃣ Работа с umask (маска прав для новых файлов)
umask 022  # По умолчанию новые файлы будут с правами 755
umask 077  # Новые файлы доступны только владельцу (700)

# 📌 7️⃣ Запрет доступа (chattr и lsattr)
sudo chattr +i myfile.txt  # Запретить изменение и удаление файла
sudo chattr -i myfile.txt  # Снять защиту
lsattr myfile.txt  # Проверить статус файла (есть ли защита)
