# Домашнее задание к занятию "`Инструменты Git`" - `Тен Денис`


### Цель задания

В результате выполнения задания вы:

* научитесь работать с утилитами Git;
* потренируетесь решать типовые задачи, возникающие при работе в команде. 

### Инструкция к заданию

1. Склонируйте [репозиторий](https://github.com/hashicorp/terraform) с исходным кодом Terraform.
2. Создайте файл для ответов на задания в своём репозитории, после выполнения прикрепите ссылку на .md-файл с ответами в личном кабинете.
3. Любые вопросы по решению задач задавайте в чате учебной группы.

------

## Задание

В клонированном репозитории:

1. Найдите полный хеш и комментарий коммита, хеш которого начинается на `aefea`.

```bash
git log --oneline | grep aefea
```
![image](https://github.com/user-attachments/assets/6a3427a1-135e-4d92-b183-30ae25d5408a)

3. Ответьте на вопросы.

* Какому тегу соответствует коммит `85024d3`?
```bash
git tag --contains 85024d3
```

![image](https://github.com/user-attachments/assets/8118ee8c-3237-43c4-b4ed-8061ed5ab10c)

* Сколько родителей у коммита `b8d720`? Напишите их хеши.

```bash
git rev-list --parents -n 1 b8d720
```
![image](https://github.com/user-attachments/assets/6145c13c-5e02-4603-b823-9ae85ecf4d4b)

* Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами  v0.12.23 и v0.12.24.

```bash
git log v0.12.23..v0.12.24 --oneline
```

![image](https://github.com/user-attachments/assets/42e99062-742d-4e9a-b92f-603237f542ed)

* Найдите коммит, в котором была создана функция `func providerSource`, её определение в коде выглядит так: `func providerSource(...)` (вместо троеточия перечислены аргументы).

```bash
git log -S 'func providerSource(' --oneline
```
![image](https://github.com/user-attachments/assets/c8ba023a-894c-45ab-a4ee-cf74d5c2813c)

* Найдите все коммиты, в которых была изменена функция `globalPluginDirs`.

```bash
git log -S 'globalPluginDirs' --oneline
```
![image](https://github.com/user-attachments/assets/c9a36ee9-944c-4cb3-9750-0042436dab7e)

Можно искать по регуляному выражению, но почему то результат другой.

```bash
git log -G 'globalPluginDirs' --oneline
```
![image](https://github.com/user-attachments/assets/1e7a3038-6048-444a-9775-bc80dcb469ae)

* Кто автор функции `synchronizedWriters`?

```bash
git log -S 'synchronizedWriters'
```
![image](https://github.com/user-attachments/assets/06bbe37b-a766-4b51-a5b4-3a67d26fe730)

Берём самый ранний коммит

```bash
git show 5ac311e2a91e381e2f52234668b49ba670aa0fe5
```
![image](https://github.com/user-attachments/assets/a7a90a3f-c268-46a0-acbe-dcaf20906e8c)

Автор: Martin Atkins <mart@degeneration.co.uk>

![image](https://github.com/user-attachments/assets/e8cdc51f-3f89-4d83-bfbc-f8f04581c061)


*В качестве решения ответьте на вопросы и опишите, как были получены эти ответы.*

---

### Правила приёма домашнего задания

В личном кабинете отправлена ссылка на .md-файл в вашем репозитории.

### Критерии оценки

Зачёт:

* выполнены все задания;
* ответы даны в развёрнутой форме;
* приложены соответствующие скриншоты и файлы проекта;
* в выполненных заданиях нет противоречий и нарушения логики.

На доработку:

* задание выполнено частично или не выполнено вообще;
* в логике выполнения заданий есть противоречия и существенные недостатки.
