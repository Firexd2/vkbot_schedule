## Описание проекта

Легкий бот для социальной сети Вконтакте, главной задачей которого является напоминание пользователей о событиях.

После ввода специальных команд программа будет напоминать личным сообщением о важном деле/событии/действии.

### Используемые технологии

В качестве обертки используется фреймворк Django. Для планировщика задач была выбрана связка Celery + Redis

### Примеры команд

```bash
!кд Таблетка 10:30,19:00 Выпей-таблетку
```
Бот будет писать каждый день в 10:30 и 19:00 сообщение ``Выпей таблетку``

Существует 5 команд разного функционала:

- на каждый день
```bash
!кд Тест 10:30,19:45 Напоминание
```

- на каждую неделю
```bash
!кн Напоминание пн,пт 12:00 Здесь-сообщение
```

- на каждый месяц
```bash
!км Название 1,5,7,8 20:30 Сообщение
```

- на каждый год
```bash
!кг ДеньРождение 06.01 09:00 Поздравить-Свету
```

- на определенный день
```bash
!д ВажныйДень 01.02.2018-10:50 Важный-день
```

Синтаксис всех команд достаточно прост, разберем подробно лишь одну.
Допустим, нужно напоминание каждую неделю в 12:00 по понедельникам и пятницам. Тогда команда будет следующая:

```bash
!кн Напоминание пн,пт 12:00 Здесь-сообщение
```

**!кн** - тип команды. **Напоминание** - название твоего расписания. **пн,пт** - понедельник и пятница,
дни недели напоминания. **12:00** - время напоминания. **Здесь-сообщение** - то сообщение,
которое будет выслано в понедельник и пятницу в 12:00. *В сообщении за место пробелов нужно использовать '-'.*

В случае ошибки бот подскажет, как исправить команду.

По-мимо команд, есть еще два действия над командами:
- Список всех расписаний: ``@с``
- Удалить расписания: ``@у НазваниеРасписания``
