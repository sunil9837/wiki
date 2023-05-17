# Setup QA Environment

- In this lab, we will we adding QA environment for our Application.

First we need to click on `Add Environment` to add the QA environment.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/53.png)

Now again we have to follow the same steps but this time these will be for QA Environment.

Now Select Environment and User Group Access that you want to give to the service and click on `Save & Continue`.

```
Environment: qa
User Role Group: QA
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/54.png)

Now you are at Service Home Page where you can choose all the steps you want to perform on this service.

It's time when we can start working with Configure CI part.

```
Click on Configure CI button that is placed on center.
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/55.png)

In this step, You can clone the same jobs from different environments as well will updated name with our current Env.

```
Choose `dev` and click on NEXT
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/56.png)

Fill the required details for `Source Details` section and click on `Continue`.

```
All these details are auto filled but feel free to change the values if you want.

GIT URL: https://github.com/OT-TRAINING/buildPiper-Workshop.git
Repo Credentials: <NOT REQUIRED>
Click on LOAD BRANCHES and choose the "MAIN" branch.
Dockerfile Path: ./Dockerfile
Image Name: {YOUR-TEAM-NAME}-app-dev/qa/qa   # This name will come automatically 
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/57.png)

Fill the required details for `CI Details` section and click on `Continue`.

```
Language: JAVA
CI Scope: NO
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/58.png)

Fill the required details for `Env Variable` section and click on `Continue`.

```
We are leaving it default for now by setting it to no
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/59.png)

Fill the required details for `Hooks` section and click on `Submit`.

```
We are leaving it default for now by setting it to no
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/60.png)

Now your job is ready for building the Image in QA Env.

Now Click on `Build` and After that again on `Build` to run the build job for Application service.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/61.png)

Click on `HISTORY`, if you want to see the status and logs of the Build Image Job.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/62.png)

As we saw that our Build Job completed successfully, Now we can move to create the Job for `Deploy` docker image for QA as well.

Again we will get the option of copy the deploy job also from other environments.

We will be choosing DEV from where we will be coping data. And everything will be auto filled. We just need to reconfirm if we need to change anything this time as we will be updating the value of Secret instead of ConfigMap as we created the secret for QA Environment instead of ConfigMAP.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/63.png)

Fill the Required Details for `Access Level` Section and click on `Continue`.

```
Service Name: {YOUR-TEAM-NAME}-app-dev-qa-qa                # This name will come automatically 
Image Name: {YOUR-TEAM-NAME}-app-dev/qa/qa                  # This name will come automatically
Deployment Name: {YOUR-TEAM-NAME}-app-dev-qa-qa             # This name will come automatically
Ingress Type: Choosing it as Public as we want this application to be public
Select Ingress: Public-Ingress
URL: {YOUR-TEAM-NAME}-app-qa.buildpiper.in
Expose Path: /
Port: 8080
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/64.png)

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

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/65.png)

Fill the Required Details for `Configuration & Secrets` Section and click on `Continue`.

```
We will we entering value from our Secret this time. And for this click on `Define From Secrets`
Select Secret: Choose the `secret` that you added while creation of Environment.
Volume Mount Path: /etc/app/config

Leave other values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/66.png)

Fill the Required Details for `Env variables` Section and click on `Continue`.

```
We will we defining runtime environment variable.

Choose "Define Raw Key Value Pairs" 
Key: SPRING_CONFIG_LOCATION
Value: /etc/app/config/

Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/67.png)

Fill the Required Details for `Node And Service Affinity` Section and click on `Continue`.

```
Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/68.png)

Fill the Required Details for `Liveness/Readiness` Section and click on `Continue`.

```
Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/69.png)

Fill the Required Details for `Lables/Annotations` Section and click on `Continue`.

```
Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/70.png)

Fill the Required Details for `Hooks` Section and click on `Submit`.

```
Leave all values as default
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/71.png)

Now our Job is created for Deploy Docker Image.

Let's deploy the image now to our cluster.

Click on `Deploy` -> Choose the `Image Tag` -> Click on `Deploy`.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/72.png)

Again Go to the "DEPLOY" under `HISTORY` section. And Check if your Deploy Job has been completed successfully.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/73.png)

We have successfully deployed our UI of application.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/74.png)

***

## Now we need to perform same steps for our MySQL Database as well to deploy it on QA Ennvironment.

Please try to perform this part of Lab on the basis of your learning. And feel free to ask questions if you are having any doubt.

# Thank You

# Happy Learning

[Next -> Lab 4](https://github.com/OT-TRAINING/buildPiper-Workshop/wiki/LAB4:-CD-Pipelines)
