# Robot operation system
### Description

Robot operation system��һ�׿�ܣ��ײ��ṩӲ���������������֧��ͨ�õ��ļ���ʽ��������ε�ʵ����Ҫ��װROS


### �����޸ĵķ���
Setup your sources.list
```
    sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" >/etc/apt/sources.list.d/ros-latest.list'
```

Set up your keys
```
    sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116
```


��װ
```
   sudo apt-get update
   sudo apt-get install ros-jade-desktop-full
```
![build settings](https://ooo.0o0.ooo/2016/11/11/58259f4663bae.jpg)

��ʼ��
```
    sudo rosdep init
    rosdep update
```
![build settings](https://ooo.0o0.ooo/2016/11/11/5825a001b90f5.jpg)

��������
```
   echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
   source ~/.bashrc
```
rosinstall
```
   sudo apt-get install python-rosinstall
```

![build settings](https://ooo.0o0.ooo/2016/11/11/5825a066675c0.jpg)



���������ǾͰ�װ��ros�� ��
### ʵ�����
����ʵ��ֻ�Ǽ򵥵İ�װһ��ros�����Ǻ��ѡ�




