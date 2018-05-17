# Инструкция по сборке библиотеки OpenCV c Qt для Python2.7

Инструкция по сборке и установке библиотеки OpenCV c Qt для python 2.7

## Установка git 

Для этого сначала нужно обновить списки пакетов

```
$ sudo apt update 
```

А затем загрузить и установить программу 

```
$ sudo apt install git  
```
После этого git будет установлен и можно переходить к его настройке. А именно, нужно глобально указать имя пользователя и электронный адрес 

```
$ git config --global user.name <username>
$ git config --global user.email <useremail>
```

#### Пример 

```
user@user:~$ git config --global user.name  User
user@user:~$ git config --global user.email usermail@gmail.com 
```

Если установлен прокси, то нужно также указать и его 

```
$ git config --global http.proxy "http://<proxy>:<port>"
```

#### Пример 

```
user@user:~$ git config --global http.proxy "http://10.128.0.100:8080"
```

## Сборка и установка библиотеки OpenCV

Склонировать в свою папку [репозиторий OpenCV](https://github.com/opencv/opencv.git). Это можно сделать с помощью команды git

```
$ git clone https://github.com/opencv/opencv.git
```

![alt text](https://github.com/serykhelena/Guides/blob/linux_os/pics_opencv_qt_pycharm/fig1_clone.png "git clone")

Перейти в папку opencv. Потом перейти на ветку 3.4.0

```
$ git checkout 3.4.0 
```

![alt text](https://github.com/serykhelena/Guides/blob/linux_os/pics_opencv_qt_pycharm/fig2_branch340.png "branch 3.4.0")

Установить все дополнительные компоненты системы. Ввести пароль, чтобы дать разрешение на установку и согласиться на предоставления необходимого места пакетам. 

```
$ sudo apt install git cmake qt5-default libeigen3-dev libtbb-dev python-numpy
```

Создать в папке opencv папку с именем build. Перейти в неё. 

```
$ mkdir build 
$ cd build 
```

В папке build вызвать команду cmake с опциями: 

```
$ cmake   -D WITH_TBB=ON \
          -D WITH_EIGEN=ON \
          -D WITH_QT=ON \
          -D CMAKE_INSTALL_PREFIX=~/opencv_bin \
          -D CMAKE_BUILD_TYPE=RELEASE \
          ..
```

При успешной сборке, конфигурация покажет примерно такое строки 

### Installing

A step by step series of examples that tell you have to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone who's code was used
* Inspiration
* etc

