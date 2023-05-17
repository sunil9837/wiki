# Micro-Service Setup

Different Sections of this LAB

* [Service Creation for Dev Database]()

  * [Build Configuration for Dev Database]()

  * [Deploy Configuration for Dev Database]()

* [Service Creation for Frontend Application UI]()

  * [Build Configuration for Frontend Application UI]()

  * [Deploy Configuration for Dev Application UI]()

For this lab we are having 2-tier application where one is for `app` and one is `database`.

* [Repo Link](https://github.com/OT-TRAINING/BuildWithBuildPiper)

It means that we will be having 2 docker images those we have to build & deploy separately and make sure these are connected with each other.

## Service Creation for Dev Database


* **As a first step In our Application Section , We need to go to the Services Section and click on `Ceate Service` button.**


![image](https://github.com/OT-TRAINING/BuildWithBuildPiper/assets/129478158/177b92a9-2f30-4f95-9518-1c6e1c7cf5b9)


*  **Choose the Service Name that you want to have and click on Save & Continue.**


   * **Name of Your Service should be `backend-db`**

![image](https://github.com/OT-TRAINING/BuildWithBuildPiper/assets/129478158/c12316f4-ec09-4803-a0d6-9c52f82fe4be)

*  **Now Select `Environment` and `User Group Access `that you want to give to the service and click on Save & Continue.**

   * **Environment: dev**
   * **User Role Group: DEVOPS**

![image](https://github.com/OT-TRAINING/BuildWithBuildPiper/assets/129478158/c6975f18-5ce8-496b-9261-f353ef4178f1)

* **Now you are at Service Home Page where you can choose all the steps you want to perform on this service.**

![image](https://github.com/OT-TRAINING/BuildWithBuildPiper/assets/129478158/7378da0b-4ff6-47a4-8ba1-2f1bfff37f04)

## BUILD Image Configuration for Dev Database:

*  **It's time when we can start working with `Configure Build` part.**

* **Scroll down and Click on `Configure Build` button that is placed on center.**

![image](https://github.com/OT-TRAINING/BuildWithBuildPiper/assets/129478158/b1df12af-0140-43f8-a912-9a700152f103)

* **Fill the required details for `Source Details` section and click on Continue.**

![image](https://github.com/OT-TRAINING/BuildWithBuildPiper/assets/129478158/5a353359-d566-42f7-93ea-d25bf4e74522)

  * **GIT URL: Spring-App : https://github.com/OT-TRAINING/BuildWithBuildPiper.git**
  * **Build Context: **

![image](https://github.com/OT-TRAINING/BuildWithBuildPiper/assets/129478158/dc968b38-4004-47b8-8072-25d2da28b64a)

* **Dockerfile Path: ./Dockerfile.mysql**
* **Image Name: backend-db/dev/dev   # This name will come automatically .**


![image](https://github.com/OT-TRAINING/BuildWithBuildPiper/assets/129478158/0032c9e5-98b8-4c0a-ae71-260077fe7f6b)

* **Fill the required details for CI Details section and click on Continue.**

  * **Language: Other       #As this service is for MySQL DB**
  * **CI Scope: NO**

![image](https://github.com/OT-TRAINING/BuildWithBuildPiper/assets/129478158/1431d5eb-f8fd-4fc4-bce5-f25a2bb88c1e)

* **Fill the required details for Env Variable section and click on Continue.**

  * **We are leaving it default for now by setting it to no and click on `Continue` button.**

![image](https://github.com/OT-TRAINING/BuildWithBuildPiper/assets/129478158/13ab2929-c523-40ee-b318-76e018ec5d73)

* **Fill the required details for Hooks section and click on Submit.**

  * **We are leaving it default for now by setting it to no**

![image](https://github.com/OT-TRAINING/BuildWithBuildPiper/assets/129478158/2468cb77-8a73-4f2c-8582-890e0ee4ec3c)

* **Now your job is ready for building the Image.**

![image](https://github.com/OT-TRAINING/BuildWithBuildPiper/assets/129478158/49df31be-be8f-4914-802c-f0a3cb8e38ed)




  




















