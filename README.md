# firstrepos


## Основные команды
```
git init: Инициализирует новый репозиторий Git в текущем каталоге.

git clone <repository>: Клонирует существующий репозиторий.

git add <file>: Добавляет файл в индекс для последующего коммита.

git commit -m "message": Фиксирует изменения в репозитории.

git status: Показывает состояние рабочего дерева.

git diff: Показывает разницу между коммитом и рабочим деревом или между коммитами.

git log: Показывает историю коммитов.

git branch: Список, создание или удаление веток.

git checkout: Переключение между ветками или восстановление рабочих файлов.

git merge: Объединение двух или более веток разработки.

git remote: Управление наборами отслеживаемых репозиториев.

git push: Отправка объектов в удаленный репозиторий.

git pull: Получение объектов из удаленного репозитория и объединение их с локальными.

git config: Позволяет просматривать и настраивать параметры конфигурации репозитория.

git help: Получение справки по командам Git.
```
## Мои действия

1. Создала учетную запись на гитхаб
2. Создала локальный репозиторий:
    ```
    git init
    ```
    
   ![](/photo/git_init.png)
3. Создала пустой текстовый документ в папке с названием *text.txt*:
   
   ![](/photo/txt1.png)
4. Добавила первую строку в текстовый документ с названием *text.txt*:
  ```
  git add text.txt
  ```
  
  Закоммитила:
  ```
  git commit -m "1 abzac"
  ```
  ![](/photo/git_commit1.png)
  
  **Так повторила 5 раз:**
  
  ![](/photo/git_commit2.png)
    
  ![](/photo/git_commit3.png)
    
  ![](/photo/git_commit4.png)
    
  ![](/photo/git_commit5.png)

  Файл в конечном итоге выглядил следующим образом:
  
  ![](/photo/texttxt.png)
    
5. Просмотрела status репозитория:
    ```
    git status
    ```
    ![](/photo/git_status.png)
6. Добавила еще один текстовый документ в папке с названием *text2.txt*:

    ![](/photo/text2.png)
8. Выполнила add и commit команды:
    ```
    git add text2.txt
    git commit -m "text2"
    ```
    ![](/photo/txt2.png)
9. Посмотрела протокол коммитов с помощью команды:
    ```
    git log
    ```
    ![](/photo/git_log.png)
10. Посмотрела изменения в файле по сравнению с последним commit:
    ```
    git diff HEAD~1 text2.txt
    ```
     ![](/photo/git_diff.png)
11. Убрала изменения относительно последнего commit из файла *text2.txt*:
    ```
    git checkout -- text2.txt
    ```
12. Посмотрела существующие ветки с помощью команды:
    ```
    git branch
    ```
    ![](/photo/git_branch.png)
13. Создала новую ветку:
    ```
    git branch branch1
    ```
    ![](/photo/git_branch1.png)
14. Переключилась на новую ветку *branch1* с помощью команды:
    ```
    git checkout branch1
    ```
    ![](/photoes/git_checkout2.png)
15. Создала новую ветку и сразу же переключилась на нее с помощью команды:
    ```
    git checkout -b branch2
    ```
    ![](/photo/git_branch2.png)
16. Удалила ветку *branch1* с помощью команды:
    ```
    git branch -d branch1
    ```
    ![](/photo/del_branch.png)
17. Добавила merge (слияние) изменения из указанной ветки в текущую с помощью команды:
    ```
    git checkout master
    git merge branch2
    ```
    ![](/photo/merge.png)
19. Создала конфликт при помощи следующих действий:
    Сначала переключилась на ветку master с помощью команды:
    ```
    git checkout master
    ```
    Изменила файл *text.txt*, добавив надпись: "6 abzac"
    Выполнила команды: add и commit
    ```
    git add text.txt
    git commit -m "add a conflict from master"
    ```
      ![](/photo/conflict1.png)

    Переключилась на ветку *branch2*:
    ```
    git checkout branch2
    ```
    Изменила файл text.txt, стерев надпись "6 abzac", и, добавив надпись: "7 abzac"
    Выполнила команды: add и commit
    
    ```
    git add text.txt
    git commit -m "add a conflict from branch2"
    ```
      ![](/photo/git_conflict2.png)
    Переключилась на ветку master и попытался выполнить merge (слияние):
      
      ```
      git checkout master
      git merge branch2
      ```
      ![](/photo/merge2.png)
21. Посмотрела в каких файлах есть конфликты при помощи команды:
    ```
    git status
    ```
    ![](/photo/git_status2.png)
22. Устранила конфликт, выполнив следующие действия:
    Так выглядит текстовый документ при конфликте:
    
    ![](/photo/conflicttxt.png)

    Стерла разметку *Git* и оставила лишь надпись: "6 abzac"
    Получилось вот так:
    
    ![](/photo/txt3.png)
    
    Выпаолнила команды: add и commit
    
    ```
    git add text.txt
    git commit -m "remove a conflict"
    ```
      ![](/photo/remove_conflict.png)
19. Переключилась на указанный коммит:
    ```
    git checkout 7699a86
    ```
    ![](/photo/7699a86.png)
18. Сделала rebase текущей ветки:
    ```
    git rebase branch2
    ```
18. Удалила ветку *rebasebranch*, которую ранее создала:
    ```
    git branch -d rebasebranch
    ```

    ![](/photo/del_branch2.png)
19. Пропустила текущий конфликтный commit:
    ```
    git rebase --skip
    ```
    ![](/photo/rebase2.png)
20. Отправила изменения из локального репозитория для указанной ветки в удаленный (дистанционный):
    ```
    git remote add origin https://github.com/ollis666/firstrepos.git
    git push origin master
    ```
21. Забрала изменения из репозитория, для которого были созданы удаленные ветки по умолчанию:
    ```
    git pull origin master
    ```
22. Забрал изменения удаленной ветки из репозитория основной ветки по умолчанию:
    
23. Клонировала репозиторий при помощи команды:
    ```
    git clone https://github.com/ollis666/firstrepos.git
    ```
