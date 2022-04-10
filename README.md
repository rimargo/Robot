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

