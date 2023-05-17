
# It's Time to start working on the Tool

<p> We have divided labs into the different parts so that we can understand each part of the BuildPiper Tool. </p>

First I would suggest you to take a clone of repo and update the URL of the `spring.datasource.url` for `"config-dev/application.properties"` & `"config-qa/application.properties"`.

- [Repo Link](https://github.com/OT-TRAINING/buildPiper-Workshop.git)

```
URL Shoul be:
For config-dev/application.properties: jdbc:mysql://{YOUR_TEAM_NAME}-db-dev-dev-dev:3306/springbootdb
For config-dev/application.properties: jdbc:mysql://{YOUR_TEAM_NAME}-db-dev-qa-qa:3306/springbootdb
```
**Above URL is basically a "{YOUR_SERVICE_NAME}:3306/databasename"**

## Environment Creation

- In this part first we will be creating 2 Environments for our application.

First go to the Environment Section and click on `Add a Environment` button and you will be redirect to the page where we can create new environment.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/2.png)

Now we need to choose `Dev` in the checkbox for `"Environment Type"` as we are creating this environment as Dev and need to fill other details as well.

```
Suggestions for Details:-
Environment Name: Dev
Select Cluster: Demo
Select Namespace: Dev
Vault Token: <Can Leave Empty>
Sonar Token: <Can Leave Empty>
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/3.png)

After filling all the details click on `save changes` button. and you will see that you have created new environment.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/4.png)

Now we can click on environment name that we have created and we can see that we are getting 2 options:
1. ConfigMap
2. Secrets 

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/5.png)

For `DEV` environment, We will be creating `ConfigMap` where we will be storing our `application.properties` config file.

You can follow the below steps to add the configmap:

**Step 1:** Under `ConfigMap Details` section click on `Add ConfigMap` from right side.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/6.png)

**Step 2:** Now fill the required details of ConfigMap

```
Config Name: application-properties
Key: application.properties
Choose `File Upload` to upload the file.
Location of file for Dev: "config-dev/application.properties"
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/7.png)

**Step3:** Click on SAVE button and Yes this is that much simple to create one ConfigMap using BuildPiper.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/8.png)

**Step4:** Click on CONTINUE button and you will see that new ConfigMap has been generated.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/9.png)

**NOTE: Follow the same steps to create `QA` Environment as well and this time we will be creating `"SECRET"`. and in the end you should be having 2 environments.**

```
Environment Type: QA
Config Name: application-properties
Key: application.properties
Choose `File Upload` to upload the file.
Location of file for Dev: "config-qa/application.properties"
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/9.png)

Here we have completed First step of our setup and now it's time to move for next step.



[Next -> Lab 2](https://github.com/OT-TRAINING/buildPiper-Workshop/wiki/LAB2:-Micro-Service-Setup)


