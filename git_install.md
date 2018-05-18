# Инструкция для установки и настройки Git 

Интсрукция по установке и настройке Git на Windows X. Также рекомендации по настройке локального и удалённого репозиториев. Руководство не предусматривает использование графического интерфейса

## Установка Git 

Зайти на [официальный сайт](https://git-scm.com/download/win) и скачать версию Git, подходящую для вашей системы 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig1.png">
</p>

Запускаем установщик. Соглашаемся с лицензионными требованиями, нажимаем Next 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig2.png">
</p>

Выбираем место для установки (оставляем по-умолчанию) 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig3.png">
</p>

Выбираем необходимые компоненты для установки (оставить по-умолчанию) 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig4.png">
</p>

Указать имя папки для Git (оставить по-умолчанию) 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig5.png">
</p>

Выбрать редактор для работы с графическим интерфейсом Git (можно выбрать любой, например Nano, но его использование в данной руководстве не предвидится).

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig6.png">
</p>

Указать переменные среды 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig7.png">
</p>

Указать используемую библиотеку для Git 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig8.png">
</p>

Настроить конвертацию конца строки 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig9.png">
</p>

Указать используемый терминал (MinTTY использует те же команды, что и Git в Linux, поэтому рекомендую его, хоть он и немного страшненький)

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig10.png">
</p>

Настроить дополнительные опции 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig11.png">
</p>

Завершить установку 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig12.png">
</p>

## Настройка удалённого репозитория 

Зайти на [сайт](https://github.com/) и зарегистрировать бесплатный аккаунт или войти в свой (если он уже существует) 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig13.png">
</p>

Нажать кнопку Start a project, чтобы создать удалённый репозиторий 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig14.png">
</p>

В открывшемся окне нужно указать имя репозитория (Repository name), описание (description) – не обязательно, выбрать тип доступа – Public (бесплатно) / Private (платно)

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig15.png">
</p>

## Связь удалённого репозитория с локальным

Создать папку (имя на английском языке, лучше без пробелов в имени), которая будет являться вашим локальным репозиторием

Открываем эту папку и в ней нажимаем правой кнопкой мыши и выбираем Git Bash Here 

<p align="left">
<img width="500" height="700" src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig16_1.png"> ![alt text](https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig16_2.png "bash_2")
</p>

Самый простой способ связать локальный и удалённый репозиторий - это «склонировать» существующий удалённый репозиторий в свой локальный. При этом, все настройки и связи образуются автоматически при «клоннировании». Для этого необходимо использовать команду git clone в папке локального репозитория

```
$ git clone URL-адрес удалённого репозитория
```

Например,

```
$ git clone URL-адрес удалённого репозитория
```

And repeat

```
$ git clone https://github.com/serykhelena/RoboPIC.git
```

Чтобы получить URL-адрес репозитория, на его странице нужно нажать кнопку Clone or download, там появится адрес страницы, его нужно скопировать. Или взять из адресной строки браузера. 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig17_1.png">
</p>
<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig17_2.png">
</p>

Если клонирование не происходит, а процесс «завис», значит Git не может добраться до сети, в таком случае необходимо настроить прокси, командой:


```
$ git config –-global http.proxy "http://<proxy>:<port>"
```

Например,

```
$ git config –-global http.proxy "http://10.128.0.100:8080"
```

После команды git clone, в локальном репозитории появится новая папка с именем вашего удалённого репозитория. Нужно зайти в неё, т.к. «склоннированный» репозиторий теперь находится в ней

```
$ cd RoboPIC 
```

Нужно открыть bash-сессию и записать глобальные настройки git (рис. 18) с помощью следующих команд:

```
$ git config –-global user.name <username>
$ git config –-global user.email <useremail>
```

После каждой команды нужно нажать Enter

<p align="left">
<img width="500" height="200" src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig15.png">
</p> 
![alt text](https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig18_2.png "git_conf_2")

Далее можно внести какие-либо изменения (например, добавить файл README.txt). После создания такого файла в терминале Git (в новой папке удалённого репозитория) ввести команду

```
$ git status
```

Данная команда покажет, какие файлы находятся в каком состоянии. После выполнения этой команды вы должны увидеть информацию по файлам, находящимся в вашем репозитории. 

```
$ git status
# On branch master
# Untracked files:
#   (use "git add <file>..." to include in what will be # committed)
#
#   README
#    nothing added to commit but untracked files
#        present (use "git add" to track)
```

Далее в терминале Git ввести команду

```
$ git add –A
```

Данная команда позволяет добавить под версионный контроль (отслеживать) новые файлы (все), если после add указать имя файла, то добавлен будет только он. 

Снова используем команду $ git status. Теперь в терминале должна появиться следующая надпись

```
$ git status
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#   new file:   README
```

Это означает, что файлу README присвоен собственный индекс и его нужно зафиксировать в репозитории. После «фиксации» вероятность потерять данный файл стремится к нулю. 

Зафиксировать изменения можно используя следующую команду

```
$ git commit –am “First commit”
```

Параметр –а заставляет Git автоматически индексировать каждый уже отслеживаемый (добавленный) на момент коммита файл. Параметр –m позволяет добавить комментарий к коммиту, так проще ориентироваться в изменениях с течением времени.

Снова используем команду $ git status. Теперь в терминале должна появиться следующая надпись

```
$ git status
# On branch master
           nothing to commit
```

Далее при помощи команды git push («толкать») можно отправить изменения в удалённый репозиторий, чтобы иметь доступ к файлам в любом месте, где есть интернет

```
$ git push 
```

При появлении дополнительного окна нужно будет ввести логин и пароль от GitHub, тем самым подтверждая, что это ваш репозиторий

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/git_install_pics/fig19.png">
</p>

Обновив страницу в удалённом репозитории, вы увидите, что все файлы из папки локального репрзитория находятся теперь и там. Обладая доступом в интернет, у вас всегда есть возможность их получить.

Для того, чтобы не загружать в удалённый репозиторий файлы, такие как MakeFile, debug и т.п. можно использовать файл .gitignore. Чтобы его создать, то в папке репозитория нужно сделать новый текстовый файл (.txt), открыть его и переименовать (.gitignore) без имени перед точкой, сохранить.

В папке должен появиться Текстовый документ с именем .gitignore. В него нужно прописать те файлы и папки, которые вы не хотите отправлять в репозиторий. В случае с проектом для микроконтроллера этот файл может содержать следующие строки

```
*/build
*/debug
*/dist
*/nproject
Makefile
```

После внесения изменений в папке локального репозитория не забудьте закоммитить измменения (= 

Если в репозиторий не добавлялись новые файлы, то можно не использовать команду git add –A, а использовать только git commit –am, данная команда отследит и добавит все изменения в уже имеющихся файлах. 

Для того чтобы добавить файлы из удалённого репозитория в локальный, нужно использовать команду («тянуть»):

```
$ git pull
```

Готовы! Теперь ваша паранойя всемирной слежки может подпитываться с помощью СКВ. Не благодарите (= 

### Полезные ссылки 

* [книга про git на русском языке](https://git-scm.com/book/ru/v1)
* [книга про git на английском языке](https://git-scm.com/book/en/v2)
* [статья на habr - быстрый старт GitHub](https://habr.com/post/125799/)
