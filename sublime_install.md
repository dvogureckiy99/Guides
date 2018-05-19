# Инструкция по установке Sublime Text 3 для Windows X

Инструкция по установке и настройке Sublime Text 3 для работы с Python 3.6.x на Windows X

## Установка текстового редактора Sublime Text 3 

Пройдя по [ссылке](https://www.sublimetext.com/3) скачать версию редактора, подходящую для вашей системы. 

Установим Sublime Text 3 для Windows 10 (64 bit) 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/sublime_install_pics/fig1.png">
</p>

Выбираем папку для установки редактора 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/sublime_install_pics/fig2.png">
</p>

Выбираем дополнительные настройки редактора, а именно нужно ли добавлять в контекстное меню проводника путь до Sublime Text 3 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/sublime_install_pics/fig3.png">
</p>

Подтверждение установки 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/sublime_install_pics/fig4.png">
</p>

## Настройка Sublime Text 3 для работы с Python 3.6.x

С [официального сайта](www.python.org) нужно скачать и установить программное обеспечение (Python 3.6.x) для используемой операционной системы. Для [Windows (64 bit)](https://www.python.org/downloads/windows/) (Download Windows x86 web-installer). Установить ПО следуя предложенным параметрам, не забудьте добавить путь до Python в переменные среды Windows!!!!

<img width="400" heigth = "400" src="https://github.com/serykhelena/Guides/blob/windows_os/sublime_install_pics/fig5_1.jpg"> <img width="400" heigth = "400" src="https://github.com/serykhelena/Guides/blob/windows_os/sublime_install_pics/fig5_2.jpg">
<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/sublime_install_pics/fig5_3.jpg">
</p>

Открыть командную строку Windows (в поиске cmd). Ввести команду

```
C:\Users\User> pip install opencv-python 
```

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/sublime_install_pics/fig6.png">
</p>

Для того, чтобы установить модуль по работе с компьютерным зрением. 
Аналогичным способом можно установить любые другие модули 

```python
pip install <module name> 
```

Открыть Sublime Text 3 и сохранить пустой проект как test.py. Для этого нужно выбрать вкладку File –> Save as … выбрать директорию и сохранить, указав имя.

Далее открыть консоль Sublime Text с помощью команды CTRL + ‘. Вставить туда следующий код и нажать Enter:

```python
import urllib.request,os,hashlib; h = '6f4c264a24d933ce70df5dedcf1dcaee' + 'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```

Проверить завершилась ли успешно установка можно, если открыть командную панель с помощью комбинации CTRL + SHIFT + P, должен появиться список параметров 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/sublime_install_pics/fig7.png">
</p>

Для того, чтобы использовать сторонние плагины для улучшения среды разработки, необходимо из командной панель выбрать пункт «Package Control: Install Package», а затем выбрать плагин, который хотите установить 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/sublime_install_pics/fig8.png">
</p>

Когда все пункты были выполнены, запустите тестовую программу

```python
print(“Hello, I am working!”)
```

Сохраните изменения с помощью «горячей» комбинации клавиш CTRL+S, далее CTRL+SHIFT+B – выберите Python, после этого код будет ассоциироваться с языком программирования Python, больше эту операцию проводить не нужно. Чтобы запустить код на исполнение нужно нажать CTRL+B (английская раскладка). Если всё было сделано правильно, то в консоли Sublime Text 3 появится надпись “Hello, I am working!” 

<p align="center">
<img src="https://github.com/serykhelena/Guides/blob/windows_os/sublime_install_pics/fig9.png">
</p>


### Готово! Кто молодец? Ты - молодец! 
