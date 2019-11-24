# Messaging with RabbitMQ
This guide walks you through the process of setting up a RabbitMQ AMQP server that publishes and subscribes to messages and creating a Spring Boot application to interact with that RabbitMQ server.

Source/Reference: https://spring.io/guides/gs/messaging-rabbitmq/


## Set up the RabbitMQ Broker in Windows
Source/Reference:
  a. https://www.rabbitmq.com/install-windows.html#installer
  b. http://www.technicalblogs.sentientmindz.com/2017/03/11/how-to-install-rabbitmq/


1) Install Erlang https://www.erlang.org/downloads--> download OTP  for 64 bit 22.1 Windows 64-bit Binary File 

    Important: the Erlang installer must be run using an administrative account otherwise a registry key expected by the RabbitMQ installer will not be present.

2) Environment variable set following
   add the variable name as “ERLANG_HOME” and set the value as “C:\Program Files\erlx.x” and click “OK” on the respective windows.

3) Once a supported version of Erlang is installed, download the RabbitMQ installer (rabbitmq-server-3.8.1.exe) and run it. It installs RabbitMQ

4) Press Windows+R to open the “Run” box. Type “cmd” into the box and then press Ctrl+Shift+Enter to run the command as an administrator

    Important : we are running command prompt as administrator--> if we dont for the following below steps we will get access denied  error in command prompt

5) Go to the rabbitmq directory
cd C:\Program Files\RabbitMQ Server\rabbitmq_server-3.8.1\sbin

6) Running the RabbitMQ broker as windows service
    i) Now run the command prompt as an administrator and go to the folder “sbin” in the RabbitMQ installation folder and from there run the following command:
    rabbitmq-service install

7) To manage the RabbitMQ Broker --> we use “RabbitMQ Management Console” and we need to enable the plugin for management console.

    Execute the following commands one by one to enable the plugin for management console:

     a) rabbitmq-plugins enable rabbitmq_management
     b) rabbitmq-service stop
     c) rabbitmq-service remove
     d) rabbitmq-service install
     e) rabbitmq-service start

8) If all goes well, we can access RabbitMQ Management Console  by hitting the URL http://localhost:15672

9) Default credentials:
      username : guest
      password : guest




