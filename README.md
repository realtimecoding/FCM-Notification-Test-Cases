

# FCM Notificaiton Test Cases


##  Motivation:
I was facing issues of getting notification in background. So I made a simple app to test fcm with more detail cases. I want to share the test cases with you. It may helps you. I am not 100% accurate If I made any mistake please correct me. I will leave this repo as open source If you want to add more details into. Thanks for reading.

<hr>

## fcm-test-case1:
![](https://github.com/shahzadafridi/FCM-Notification-Test-Cases/blob/main/fcm-test-case1.png?raw=true)

######  FCM Notification:

If the fcm notificaiton has inculdes **data** & **notification** both and the app is in **foreground** then you will recieve both (data and notificaiton) in **onMessageReceived** there you can handle them.

######  fcm-test-case1-diagram:
![](https://github.com/shahzadafridi/FCM-Notification-Test-Cases/blob/main/fcm-test-case1-diagram.PNG?raw=true)

<hr>

## fcm-test-case2:
![](https://github.com/shahzadafridi/FCM-Notification-Test-Cases/blob/main/fcm-test-case2.png?raw=true)

######  FCM Notification:

If the fcm notificaiton has inculdes **data** & **notification** both and the app is in **background** then you will recieve only notification which is handled by FCM itself. You would not recieve anything in **onMessageReceived**.

If you click on notification then It will lunch **luncher activity **. If the fcm notificaiton request has **data** along with **notificaiton**. and you need the values inside data payload then you can get them from intent of luncher activity e-g

Inside **onCreate** of Luncher Activity ->** getInent().getStringExtra("test");**
**"test"** is a key value pair inside data payload. In your case write the matched key which you have put in data payload.

######  fcm-test-case2-diagram:
![](https://github.com/shahzadafridi/FCM-Notification-Test-Cases/blob/main/fcm-test-case2-diagram.PNG?raw=true)

<hr>

## fcm-test-case3:
![](https://github.com/shahzadafridi/FCM-Notification-Test-Cases/blob/main/fcm-test-case3.png?raw=true)

######  FCM Notification:

If app is killed then you might not recieve notificaiton. Sometimes It happens when you killed app and send notification to device then nothing happen on your device.

######  fcm-test-case3-diagram:
![](https://github.com/shahzadafridi/FCM-Notification-Test-Cases/blob/main/fcm-test-case3-diagram.PNG?raw=true)

<hr>

## fcm-test-case4:
![](https://github.com/shahzadafridi/FCM-Notification-Test-Cases/blob/main/fcm-test-case4.png?raw=true)

######  FCM Notification:

**Extended fcm-test-case3** - If the fcm-test-case3 happens then you open the app and closed it. Send fcm notificaiton then you will start recieving notificaitons, fresh and pending notifications as well (In fcm-test-case3 not recieved notificaitons which was in pending state)

######  fcm-test-case4-diagram:
![](https://github.com/shahzadafridi/FCM-Notification-Test-Cases/blob/main/fcm-test-case4-diagram.PNG?raw=true)

<hr>

## fcm-test-case5:
![](https://github.com/shahzadafridi/FCM-Notification-Test-Cases/blob/main/fcm-test-case5.png?raw=true)

**Extended fcm-test-case2** - (repeating) If the fcm notificaiton has inculdes **data** & **notification** both and the app is in **background** then you will recieve only notification which is handled by FCM itself. You would not recieve anything in **onMessageReceived**.

------------


Now If you remove **notification** payload from request and left only **data** then you will get **data** payload in **onMessageReceived** and **notificaiton** will null If the app is in **background**.

If the app is in **foreground** then you will get only **data** and **notification** will null because we didn't inculde notification payload to fcm request.

If the app is **killed** you will recieve data payload in **onMessageReceived** there you can handle it with cutsom notificaiton to notify user and can get data values to perform your actions.

######  fcm-test-case5-diagram:
![](https://github.com/shahzadafridi/FCM-Notification-Test-Cases/blob/main/fcm-test-case5-diagram.PNG?raw=true)]

<hr>

## fcm-test-case6:
![](https://github.com/shahzadafridi/FCM-Notification-Test-Cases/blob/main/fcm-test-case6.png?raw=true)
 
Now If you remove **data** payload from request and left only **notificaiton** then you will get **notificaiton** payload in **onMessageReceived** and **data** will null.

If the app is in **background** then you will not recieve notification payload in **onMessageReceived**. you will recieve only notification which is handled by FCM itself.

If the app is **killed** you will recieve only notification which is handled by FCM itself. If you click on notificaiton it will redirect to luncher activity.

######  fcm-test-case6-diagram:
![](https://github.com/shahzadafridi/FCM-Notification-Test-Cases/blob/main/fcm-test-case6-diagram.PNG?raw=true)

 
