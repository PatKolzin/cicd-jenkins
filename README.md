# Домашнее задание к занятию 10 «Jenkins»

## Подготовка к выполнению

1. Создать два VM: для jenkins-master и jenkins-agent.
![1](https://github.com/PatKolzin/cicd-jenkins/assets/75835363/d7162687-572c-4ae3-8a43-6ac291b1496b)

2. Установить Jenkins при помощи playbook.
3. Запустить и проверить работоспособность.
4. Сделать первоначальную настройку.
![2](https://github.com/PatKolzin/cicd-jenkins/assets/75835363/03fedc8d-a41e-4b11-93dd-eb6f6cb4b0c8)

## Основная часть

1. Сделать Freestyle Job, который будет запускать `molecule test` из любого вашего репозитория с ролью.
![3](https://github.com/PatKolzin/cicd-jenkins/assets/75835363/dc7bd74e-fb74-4366-aa8d-597edf8e6a5e)
![4](https://github.com/PatKolzin/cicd-jenkins/assets/75835363/1e1b0248-f2e8-4e3a-9a8f-3dca4198f49a)

2. Сделать Declarative Pipeline Job, который будет запускать `molecule test` из любого вашего репозитория с ролью.
![5](https://github.com/PatKolzin/cicd-jenkins/assets/75835363/0eb37eb6-a76b-4304-9c56-43d3c486fc06)

3. Перенести Declarative Pipeline в репозиторий в файл `Jenkinsfile`.
![6](https://github.com/PatKolzin/cicd-jenkins/assets/75835363/5f6c5e6d-ea12-4776-8600-ae522900aa26)

4. Создать Multibranch Pipeline на запуск `Jenkinsfile` из репозитория.
![7](https://github.com/PatKolzin/cicd-jenkins/assets/75835363/4fde06d7-0739-4f7c-8a80-aca50bb46520)

5. Создать Scripted Pipeline, наполнить его скриптом из [pipeline](./pipeline).
![8](https://github.com/PatKolzin/cicd-jenkins/assets/75835363/7226032a-5555-4bab-abe6-5123a37851c2)

6. Внести необходимые изменения, чтобы Pipeline запускал `ansible-playbook` без флагов `--check --diff`, если не установлен параметр при запуске джобы (prod_run = True). По умолчанию параметр имеет значение False и запускает прогон с флагами `--check --diff`.
![9](https://github.com/PatKolzin/cicd-jenkins/assets/75835363/3b602911-170e-4fba-ab99-d0488d8fb2d0)

7. Проверить работоспособность, исправить ошибки, исправленный Pipeline вложить в репозиторий в файл `ScriptedJenkinsfile`.
![10](https://github.com/PatKolzin/cicd-jenkins/assets/75835363/6013b70d-c059-4b07-9d8b-9415b43fdf82)

8. Отправить ссылку на репозиторий с ролью и Declarative Pipeline и Scripted Pipeline.  
[Vector-role](https://github.com/PatKolzin/vector-role-molecule/tree/main/)  
[Declarative_Pipeline](https://github.com/PatKolzin/vector-role-molecule/blob/main/Jenkinsfile)  
[Scripted_Pipeline](https://github.com/PatKolzin/vector-role-molecule/blob/main/ScriptedJenkinsfile)  



## Необязательная часть

1. Создать скрипт на groovy, который будет собирать все Job, завершившиеся хотя бы раз неуспешно. Добавить скрипт в репозиторий с решением и названием `AllJobFailure.groovy`.
2. Создать Scripted Pipeline так, чтобы он мог сначала запустить через Yandex Cloud CLI необходимое количество инстансов, прописать их в инвентори плейбука и после этого запускать плейбук. Мы должны при нажатии кнопки получить готовую к использованию систему.

---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.

---
