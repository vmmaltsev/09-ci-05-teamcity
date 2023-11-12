# Домашнее задание к занятию 11 «Teamcity» - `Мальцев Виктор`

---

# В соответствии с условиями задания сделан fork репозитория https://github.com/aragastmatb/example-teamcity
# Дальнейшая работа проведена в репозитории https://github.com/vmmaltsev/example-teamcity.git

# Создан jetbrains/teamcity-server, который доступен по ссылке http://158.160.106.182:8111/

![teamcity-server](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_48.png)

# Создан jetbrains/teamcity-agent, проведена авторизация агента на jetbrains/teamcity-server

![teamcity-agent](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_49.png)

![teamcity-agent](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_50.png)

![teamcity-agent](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_51.png)

# Создан nexus репозиторий с помощью Ansible

![teamcity-agent](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_52.png)


1. Создайте новый проект в teamcity на основе fork.
2. Сделайте autodetect конфигурации.
3. Сохраните необходимые шаги, запустите первую сборку master.
4. Поменяйте условия сборки: если сборка по ветке master, то должен происходит mvn clean deploy, иначе mvn clean test.
5. Для deploy будет необходимо загрузить settings.xml в набор конфигураций maven у teamcity, предварительно записав туда креды для подключения к nexus.
6. В pom.xml необходимо поменять ссылки на репозиторий и nexus.
7. Запустите сборку по master, убедитесь, что всё прошло успешно и артефакт появился в nexus.
8. Мигрируйте build configuration в репозиторий.
9. Создайте отдельную ветку feature/add_reply в репозитории.
10. Напишите новый метод для класса Welcomer: метод должен возвращать произвольную реплику, содержащую слово hunter.
11. Дополните тест для нового метода на поиск слова hunter в новой реплике.
12. Сделайте push всех изменений в новую ветку репозитория.
13. Убедитесь, что сборка самостоятельно запустилась, тесты прошли успешно.
14. Внесите изменения из произвольной ветки feature/add_reply в master через Merge.
15. Убедитесь, что нет собранного артефакта в сборке по ветке master.
16. Настройте конфигурацию так, чтобы она собирала .jar в артефакты сборки.
17. Проведите повторную сборку мастера, убедитесь, что сбора прошла успешно и артефакты собраны.
18. Проверьте, что конфигурация в репозитории содержит все настройки конфигурации из teamcity.
19. В ответе пришлите ссылку на репозиторий.