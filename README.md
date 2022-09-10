How to Use
Step 1:

Download or clone this repo by using the link below:

https://github.com/rethuna/EventDemo.git

Step 2:

Go to project root and execute the following command in console to get the required dependencies:

flutter pub get 

Implementation
1.Creating a dynamic link in the console
2.Handling it in the application
3.Checking the deeplink url and perform navigations
4.Create a dynamic link programatically
5.Debug deeplink and behaviour tips

Step 3:

Create a dynamic link progrmatically

This is also quite a straight forward task. Remember those 5 things you had to to when creating a dynamic link in the console, you do that but in code. In the DynamicLinkService create a new function that returns a future called createFirstPostLink that takes in a String title to share. In this function we will define all the dynamic link parameters and return the Uri.toString() as the result to the caller

Debug Deeplink and behaviour tips
![image](https://user-images.githubusercontent.com/6903524/189453137-40029e87-2548-43e0-8918-a08260bf00cf.png)

Using the deep link technique you can get to anywhere in your app with the correct parameters and provide the user with the best experience possible when they click your links.

Step 4:

Firebase Push Notification(Using Dynamic Link)

Implement server side notification using deep dynamic link. When the notification is enabled, the user is redirected to the project home when they click on the link page.

Step 5:

Here iam using Postman for testing purposes(https://github.com/alisonhall/postman-introduction/blob/master/README.md)

Set your HTTP request to POST.
Input the link in request url like this: https://fcm.googleapis.com/fcm/send
Switch to Head Tab,

then select key as Content type and value as application/json,
next select key as Authorization and value key=AAAAVp06ckQ:APA91bFnvz1sKtKWL6KM6uFKDyu450nVnNmpEH84Q25z-cQiF3pzIANWnTjyE9v8bsgbWSE2r_DfLQ7oNlfxFEAg5rg7i7x69JqJitQNT7v4KVD6bEgQDgFCNiEdFaGHEoKeQZ8eI4HO


![post](https://user-images.githubusercontent.com/6903524/189455744-c263227d-d230-4aee-9bf4-d11534612cc8.PNG)

Switch to the Body tab,
then Click a content type. If sending JSON data, click "raw".

![image](https://user-images.githubusercontent.com/6903524/189454736-3af7f65b-4969-401f-996b-813f6645ca79.png)


then inside row write this code

{
    "registration_ids": [
        "eBPizinSQ9Gstzp-M4igWP:APA91bHFIqfS6mateYwp8DKEq5ETpuFMLUr5wUq2QVp4Rxwhm485JdT_E-ZYyyNDDtYKaIwEHmFZjxqwWs1hk3_9y8ctUwyI95jPspHeHy__J3getglJ5UTi8oLL475_ENmMn_sjmH2T"
    ],
    "notification": {
        "body": "Invitation Message",
        "title": "Event Invitation",
        "android_channel_id": "pushnotificationapp",
        "image":"https://firebasestorage.googleapis.com/v0/b/event-dynamic-link.appspot.com/o/a.jpg?alt=media&token=34c32db3-671c-4715-a327-6a8e11b1a84f"
        "sound": false
    }
}

This "registration_ids" is the device token so we should copy the device token from this application and change the token accordingly.

![Screenshot_20220910_041121](https://user-images.githubusercontent.com/6903524/189455227-4b6046a4-2295-4659-b9ae-b8652230c818.jpg)

From this setting icon we can copy the device token.then Click Send.

