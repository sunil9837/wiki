# CD Pipelines

In this lab we will be using most important feature of `BuildPiper` i.e. `"CD Pipelines"`.

## Let's Start 

```
First we need to click on `Add Pipeline` under `Pipelines` section.
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/75.png)

First fill the below mentioned details and then click on `Save`.

```
Now Enter the required details to create a pipeline:
Pipeline Name: CD-Pipeline
Retention Count: 5
How you want to trigger the pipeline?: Choose Manual
Services: Choose All Services
Tags: dev , cd , devops                   # Anything you want
Roles: Can choose QA and DevOps           # People with those roles will only be able to see your Pipeline
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/76.png)

Now Your `Basic Info` for Pipeline is created. It's time to create `Stages` & `Jobs` for the pipeline.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/77.png)

First We will create `dev` stage.

Click on `Add New Stage` button and enter below details and click on `ADD`

```
Stage Name: DEV
Approval Required?: NO
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/78.png)

Now Your Dev Stage has been created.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/79.png)

It's time to add `Jobs` inside our `DEV` stage.

Click on `Add New Job` button and after entering details click on `ADD` button.

```
Job Type: Build
From Environment: dev
Services: ALL

Other options we can leave as default.
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/80.png)

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/81.png)

Now perform the same process to create another job for `Deploy`.

After Entering all required details click on `ADD`.

```
Job Type: Deploy
From Environment: dev
Services: ALL
Artifact Source: Latest
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/82.png)

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/83.png)

As we are done with creation for All Jobs for DEV Stage. Now we are good to move for Next Step i.e. Next Stage for QA.

***

Let's create QA Stage now.

As expected, Click on `Add New Stage` button and Enter required details and click on `ADD`.

```
Stage Name: DEV
Approval Required?: YES                   # This time we want approval before start execution of Job.
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/84.png)

Again click on `Add New Job` for creating the Job for QA Stage.

```
Job Type: Build
From Environment: qa
Services: ALL

Other options we can leave as default.
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/85.png)

Now perform the same process to create another job for `Deploy`.

After Entering all required details click on `ADD`.

```
Job Type: Deploy
From Environment: qa
Services: ALL
Artifact Source: Latest
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/86.png)

Click on `Save Workflow` to save your pipeline.

**Feel Free to explore YAML view as well of the Pipeline that you just have created.**

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/87.png)

Click on `Pipeline Overview` link places left side on your screen and Click `RUN (Little Play LOGO)` to trigger the Pipeline.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/88.png)

And You will see that Pipeline has been triggered and first stage will be running.

**Feel Free to explore more clicking the links on Pipeline.**

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/89.png)

As for `QA` stage we added that `APPROVAL REQUIRED` to `YES` so job is waiting for `APPROVAL`.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/90.png)

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/91.png)

After Approving the Jobs for QA Stage, Every job shoule complete fine.

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/92.png)

And this is how our End result will look like.

```
Enter the URL on your web account that you mentioned at the time of your application deployment.
```

![](https://github.com/OT-TRAINING/buildPiper-Workshop/blob/images/images/93.png)

# Thank You

# Happy Learning
