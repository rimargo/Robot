# Robot
Симуляция управления роботом Робот с ПИД-регулятором, управление которым осуществляется с помощью клавиатуры, используя ROS.
# Порядок действий
1) Скопировать папку beginner_tutorial в catckin_ws/src
2) Для управления симуляцией нужно клонировать репозиторий https://github.com/ROBOTISGIT/turtlebot3 в ~/catkin_ws/src 
3) Скачать библиотеки numpy и matplotlib.
4) Собрать проект
$ catkin_make --only-pkg-with-deps robot_sim
5) В первом терминале запустить ядро Ros
$ roscore
6) Через второй терминал запустить клонированный репозиторий с GitHub 
$ export TURTLEBOT3_MODEL=waffle; roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
7) Через третий терминал запустить скрипт listener.py
$ rosrun beginner_tutorial listener.py
8) Через четвертый терминал запустить скрипт talker.py
$ rosrun beginner_tutorial talker.py
# Работа скриптов:
1. Скрипт turtlebot3_teleop находится в репозитории GitHub. Он предназначен для управления робота с помощью кнопок клавиатуры. При запуске появляется инструкция по управлению.
В консоль выводится значения линейных и угловых скоростей, которые изменяются при нажатии на кнопки: 
Currently: linear vel 0.0 angular vel 0.0
2. Скрипт listener.py будет выводить в консоль cтроку, в которой отображается время получения сообщения и значения, полученные с левого и правого энкодеров. 
[INFO] [169934.9949]: time: 1622883847745637737 left encoder 147868 right encoder 24484
3. Скрипт talker.py в консоль ничего не выводит, а выводит дополнительное окно с графиком отрисованной траектории. Траектория выводится при прошествии 20 секунд после запуска talker.py.
Траекторию можно выводить одну на выбор:
•	Траектория желаемого движения (figure 1)
•	Траектория реального движения при работе регулятора (figure 2)
Для того, чтобы выбрать, какая траектория будет отрисовываться, достаточно закомментировать 4 строчки в коде:
•	В функции «def ref_draw(new_coord)» закомментировать 
«if (len(x) and len(y)) == 200:
plt.figure(1)
plt.plot(x, y)
plt.show()»
 тогда выведется желаемая.
•	В функции «def real_draw(new_encoders)» закомментировать 
«if (len(real_y) and len(real_x)) == 200:
plt.figure(2)
plt.plot(real_x, real_y)
plt.show()»
 тогда выведется реальная.

