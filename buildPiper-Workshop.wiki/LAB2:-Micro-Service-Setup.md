
# Micro-Service Setup

**Different Sections of this LAB**

- [Service Creation for Dev Database](https://github.com/OT-TRAINING/buildPiper-Workshop/wiki/LAB2:-Micro-Service-Setup#service-creation-for-dev-database)

     - [Build Configuration for Dev Database](https://github.com/OT-TRAINING/buildPiper-Workshop/wiki/LAB2:-Micro-Service-Setup#build-image-configuration-for-dev-database)

     - [Deploy Configuration for Dev Database](https://github.com/OT-TRAINING/buildPiper-Workshop/wiki/LAB2:-Micro-Service-Setup#deploy-image-configuration-for-dev-database)

- [Service Creation for Dev Application UI](https://github.com/OT-TRAINING/buildPiper-Workshop/wiki/LAB2:-Micro-Service-Setup#service-creation-for-dev-application-ui)

     - [Build Configuration for Dev Application UI](https://github.com/OT-TRAINING/buildPiper-Workshop/wiki/LAB2:-Micro-Service-Setup#build-image-configuration-for-dev-application-ui)

     - [Deploy Configuration for Dev Application UI](https://github.com/OT-TRAINING/buildPiper-Workshop/wiki/LAB2:-Micro-Service-Setup#deploy-image-configuration-for-dev-application-ui)

For this lab we are having 2-tier application where one is for `app` and one is `database`.

- [Repo Link](https://github.com/OT-TRAINING/buildPiper-Workshop.git)

It means that we will be having 2 docker images those we have to build & deploy separately and make sure these are connected with each other.

## Service Creation for Dev Database

```
As a first step In our Application Section , We need to go to the Services Section and click on `Add Service` button.
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/10.png)

Choose the Service Name that you want to have and click on `Save & Continue`.

```
Name of Your Service: {YOUR-TEAM-NAME}-db-dev
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/11.png)

Now Select `Environment` and `User Group Access` that you want to give to the service and click on `Save & Continue`.

```
Environment: dev
User Role Group: DEV
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/12.png)

Now you are at Service Home Page where you can choose all the steps you want to perform on this service.

### BUILD Image Configuration for Dev Database

It's time when we can start working with `Configure CI` part.

Click on `Configure CI` button that is placed on center.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/13.png)

Fill the required details for `Source Details` section and click on `Continue`.

```
GIT URL: https://github.com/OT-TRAINING/buildPiper-Workshop.git
Repo Credentials: <NOT REQUIRED>
Click on LOAD BRANCHES and choose the "MAIN" branch.
Dockerfile Path: ./Dockerfile.mysql
Image Name: {YOUR-TEAM-NAME}-db-dev/dev/dev   # This name will come automatically 
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/14.png)

Fill the required details for `CI Details` section and click on `Continue`.

```
Language: Other       #As this service is for MySQL DB
CI Scope: NO
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/15.png)

Fill the required details for `Env Variable` section and click on `Continue`.

```
We are leaving it default for now by setting it to no
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/16.png)

Fill the required details for `Hooks` section and click on `Submit`.

```
We are leaving it default for now by setting it to no
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/17.png)

Now your job is ready for building the Image.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/18.png)

Now Click on `Build` and After that again on `Build` to run the build job for Database service.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/19.png)

Click on `HISTORY`, if you want to see the status and logs of the Build Image Job.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/20.png)

As we saw that our Build Job completed successfully, Now we can move to create the Job for `Deploy` docker image.

### Deploy Image Configuration for Dev Database

To Deploy the Image first we need to configure `DEPLOY DETAILS`. And to perform this task we will be do doing it using `BuildPiper-UI`. So click on `Continue` for BuildPiper-UI section.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/21.png)

Fill the Required Details for `Access Level` Section and click on `Continue`.

```
Service Name: {YOUR-TEAM-NAME}-db-dev-dev-dev              # This name will come automatically 
Image Name: {YOUR-TEAM-NAME}-db-dev/dev/dev                # This name will come automatically
Deployment Name: {YOUR-TEAM-NAME}-db-dev-dev-dev           # This name will come automatically
Ingress Type: Choosing it as Private as it is Database
Port: 3306
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/22.png)

Fill the Required Details for `Request Quota` Section and click on `Continue`.

```
We will be updating values for Memory and CPU Quota.
Request Memory Quota: 500
Request CPU Quota: 500

Leave other values as default
````

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/23.png)

Fill the Required Details for `Configuration & Secrets` Section and click on `Continue`.

```
Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/24.png)

Fill the Required Details for `Env variables` Section and click on `Continue`.

```
Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/25.png)

Fill the Required Details for `Node And Service Affinity` Section and click on `Continue`.

```
Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/26.png)

Fill the Required Details for `Liveness/Readiness` Section and click on `Continue`.

```
Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/27.png)

Fill the Required Details for `Lables/Annotations` Section and click on `Continue`.

```
Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/28.png)

Fill the Required Details for `Hooks` Section and click on `Submit`.

```
Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/29.png)

Now our Job is created for Deploy Docker Image.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/30.png)

Let's deploy the image now to our cluster.

Click on `Deploy` -> Choose the `Image Tag` -> Click on `Deploy`.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/31.png)

Again Go to the "DEPLOY" under `HISTORY` section. And Check if your Deploy Job has been completed successfully.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/32.png)

We have successfully deployed our MySQL database.

***

## Service Creation for Dev Application UI

Now it's time when we have to setup another Service for our `Application UI` as well.

We will be performing same steps as we performed for `Database Service` setup except this time we will be using `ConfigMap` that we added while creating our `DEV Environment`.

**Let's Start again and this time try it creating without following the steps mentioned here**

Click on `Add New Service` and Choose the Service Name that you want to have and click on Save & Continue.

```
Name of Your Service: {YOUR-TEAM-NAME}-app-dev
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/33.png)

Now Select `Environment` and `User Group Access` that you want to give to the service and click on `Save & Continue`.

```
Environment: dev
User Role Group: DEV
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/34.png)

Now you are at Service Home Page where you can choose all the steps you want to perform on this service.

It's time when we can start working with `Configure CI` part.

### BUILD Image Configuration for Dev Application UI

Click on `Configure CI` button that is placed on center.

Fill the required details for `Source Details` section and click on `Continue`.

```
GIT URL: https://github.com/OT-TRAINING/buildPiper-Workshop.git
Repo Credentials: <NOT REQUIRED>
Click on LOAD BRANCHES and choose the "MAIN" branch.
Dockerfile Path: ./Dockerfile
Image Name: {YOUR-TEAM-NAME}-app-dev/dev/dev   # This name will come automatically 
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/35.png)

Fill the required details for `CI Details` section and click on `Continue`.

```
Language: JAVA
CI Scope: NO
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/36.png)

Fill the required details for `Env Variable` section and click on `Continue`.

```
We are leaving it default for now by setting it to no
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/37.png)

Fill the required details for `Hooks` section and click on `Submit`.

```
We are leaving it default for now by setting it to no
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/38.png)

Now your job is ready for building the Image.

Now Click on `Build` and After that again on `Build` to run the build job for Application service.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/39.png)

Click on `HISTORY`, if you want to see the status and logs of the Build Image Job.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/40.png)

As we saw that our Build Job completed successfully, Now we can move to create the Job for `Deploy` docker image.

### Deploy Image Configuration for Dev Application UI

To Deploy the Image first we need to configure `DEPLOY DETAILS`. And to perform this task we will be do doing it using `BuildPiper-UI`. So click on `Continue` for BuildPiper-UI section.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/41.png)

Fill the Required Details for `Access Level` Section and click on `Continue`.

```
Service Name: {YOUR-TEAM-NAME}-app-dev-dev-dev              # This name will come automatically 
Image Name: {YOUR-TEAM-NAME}-app-dev/dev/dev                # This name will come automatically
Deployment Name: {YOUR-TEAM-NAME}-app-dev-dev-dev           # This name will come automatically
Ingress Type: Choosing it as Public as we want this application to be public
Select Ingress: Public-Ingress
URL: {YOUR-TEAM-NAME}-app-dev.buildpiper.in
Expose Path: /
Port: 8080
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/42.png)

Fill the Required Details for `Request Quota` Section and click on `Continue`.

```
We will be updating values for Memory and CPU Quota.
Request Memory Quota: 500
Request CPU Quota: 500

Updating the LIMIT QUOTA as well this time.
Limit Memory Quota: 1000
Limit CPU Quota: 1000

Leave other values as default
````

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/43.png)

Fill the Required Details for `Configuration & Secrets` Section and click on `Continue`.

```
We will we entering value from our ComfigMap this time. And for this click on `Define From ConfigMap`
Select ConfigMap: Choose the configMap that you added while creation of Environment.
Volume Mount Path: /etc/app/config

Leave other values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/44.png)

Fill the Required Details for `Env variables` Section and click on `Continue`.

```
We will we defining runtime environment variable.

Choose "Define Raw Key Value Pairs" 
Key: SPRING_CONFIG_LOCATION
Value: /etc/app/config/

Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/45.png)

Fill the Required Details for `Node And Service Affinity` Section and click on `Continue`.

```
Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/46.png)

Fill the Required Details for `Liveness/Readiness` Section and click on `Continue`.

```
Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/47.png)

Fill the Required Details for `Lables/Annotations` Section and click on `Continue`.

```
Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/48.png)

Fill the Required Details for `Hooks` Section and click on `Submit`.

```
Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/49.png)

Now our Job is created for Deploy Docker Image.

Let's deploy the image now to our cluster.

Click on `Deploy` -> Choose the `Image Tag` -> Click on `Deploy`.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/50.png)

Again Go to the "DEPLOY" under `HISTORY` section. And Check if your Deploy Job has been completed successfully.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/51.png)

We have successfully deployed our UI of application.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/52.png)


# Thank You

# Happy Learning

[Next -> Lab 3](https://github.com/OT-TRAINING/buildPiper-Workshop/wiki/LAB3:-Setup-QA-Environment)