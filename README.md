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

![nexus](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_52.png)


# Решение:

1. Создайте новый проект в teamcity на основе fork.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_53.png)


2. Сделайте autodetect конфигурации.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_54.png)

3. Сохраните необходимые шаги, запустите первую сборку master.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_55.png)

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_56.png)

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_57.png)

4. Поменяйте условия сборки: если сборка по ветке master, то должен происходит mvn clean deploy, иначе mvn clean test.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_59.png)

5. Для deploy будет необходимо загрузить settings.xml в набор конфигураций maven у teamcity, предварительно записав туда креды для подключения к nexus.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_60.png)

6. В pom.xml необходимо поменять ссылки на репозиторий и nexus.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_61.png)

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_62.png)

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_63.png)

7. Запустите сборку по master, убедитесь, что всё прошло успешно и артефакт появился в nexus.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_64.png)

8. Мигрируйте build configuration в репозиторий.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_65.png)

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_66.png)

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_67.png)

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_68.png)

9. Создайте отдельную ветку feature/add_reply в репозитории.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_69.png)

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_70.png)

10. Напишите новый метод для класса Welcomer: метод должен возвращать произвольную реплику, содержащую слово hunter.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_75.png)

11. Дополните тест для нового метода на поиск слова hunter в новой реплике.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_76.png)

12. Сделайте push всех изменений в новую ветку репозитория.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_77.png)

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_78.png)

13. Убедитесь, что сборка самостоятельно запустилась, тесты прошли успешно.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_79.png)

14. Внесите изменения из произвольной ветки feature/add_reply в master через Merge.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_80.png)

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_81.png)

15. Убедитесь, что нет собранного артефакта в сборке по ветке master.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_82.png)

16. Настройте конфигурацию так, чтобы она собирала .jar в артефакты сборки.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_83.png)

17. Проведите повторную сборку мастера, убедитесь, что сбора прошла успешно и артефакты собраны.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_84.png)

18. Проверьте, что конфигурация в репозитории содержит все настройки конфигурации из teamcity.

![alt text](https://github.com/vmmaltsev/screenshot/blob/main/Screenshot_85.png)

19. В ответе пришлите ссылку на репозиторий.

https://github.com/vmmaltsev/example-teamcity.git
