<p align="center">
<!-- https://user-images.githubusercontent.com/48657780/175860913-cad6770a-6378-46f0-836a-e2c11dcd0430.png --> 
<!-- The Alternative Preview made by K.Sherif -->
<!-- The Original Preview made by Abanoub -->
<img src="https://user-images.githubusercontent.com/48348589/188187299-9308dda6-d65f-40bf-84f1-e510d1c8fc77.jpg"/>
</p>

<div align="center">
 
 <!-- REPO FAST LINKS -->
[![GitHub contributors](https://img.shields.io/github/contributors/KAN-Team/Careium-AI)](https://github.com/KAN-Team/Careium-AI/contributors)
[![GitHub issues](https://img.shields.io/github/issues/KAN-Team/Careium-AI)](https://github.com/KAN-Team/Careium-AI/issues)
[![GitHub forks](https://img.shields.io/github/forks/KAN-Team/Careium-AI)](https://github.com/KAN-Team/Careium-AI/network)
[![GitHub stars](https://img.shields.io/github/stars/KAN-Team/Careium-AI)](https://github.com/KAN-Team/Careium-AI/stargazers)
[![GitHub license](https://img.shields.io/github/license/KAN-Team/Careium-AI)](https://github.com/KAN-Team/Careium-AI/blob/master/LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/KAN-Team/Careium-AI)](https://github.com/KAN-Team/Careium-AI/commits)

</div>


# Careium-AI

&nbsp; &nbsp; &nbsp; &nbsp; At this extreme moment, we began working from home, away from campus,
and keeping social distance from as many people as possible. As we stay home and
stick with the foods that have been in our fridge, we are temporarily living a
sedentary lifestyle with increased odds of physical inactivity, excessive eating and
sitting, stress, anxiety, and depression. Many of us will gain some weight during
the pandemic and may keep the extra weight permanently, which may carry
considerable health risks for type 2 diabetes, hypertension, heart attack, stroke, and
other health problems. This is where the importance of **Careium Artificial
Intelligence (AI) Food Tracker** comes in.

&nbsp; &nbsp; &nbsp; &nbsp; Accordingly, the **Careium-AI Food Tracker** (Android) application helps
diabetes, liver patients, and those who want to track their health throughout the day
through daily meals by calculating the calories and minerals per each meal by
taking a picture of the meal, and the application detects the food type and analyzes
its calories and minerals. Also, the application follows up gaining or losing weight,
or even avoiding some food due to allergies. That is achieved using Deep Learning
and Image Processing.

&nbsp; &nbsp; &nbsp; &nbsp; **Careium-AI Food Tracker** shows astonishing results compared to what
was expected for a simple use case example. Capturing the food plate, long dish,
deep dish or even scattered amount of food, Careium can still segment the food
region, process it and predicts the main five **nutrition components** *<ins>(Calories,
Mass, Fat, Carbs, Proteins)</ins>*. Calories are measured in `cal`, all others are measured
in `grams`. It can be used in **classifying** a mixed dish of food into multiple food
categories, generating food eaten **reports** periodically, **recommending** a proper
meal from a set of different available meals in a given dataset and giving **alarms**
for each mealtime.

<img src="https://user-images.githubusercontent.com/48657780/175862136-a5da5362-0531-4785-9cbf-14fc4f18bbe9.png" align="right" width="25%" height="60%"></img>

## 🥣 Features

<div style="display:flex;">

- Providing weekly reports
- Meals' time alarm
- Capturing an image of the eaten food plate
- Recognizing the food ingredients
- Predicting the food nutrients (calories, fats, carbs, proteins)
- Other user profile manipulations e.g. (profile viewing/editing, login/register authentication, etc...)

</div>

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<!-- TABLE OF CONTENTS -->
## 🗂️ Table of Contents

<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#-background"> ➤ Background</a>
      <ul>
        <li><a href="#paper-1">Paper 1: Food Detection and Recognition using CNN</a></li>
        <li><a href="#paper-2">Paper 2: Food Recognition - New Dataset, Experiments and Results</a></li>
        <li><a href="#paper-3">Paper 3: DL-Based Food Calorie Estimation</a></li>
        <li><a href="#survey-of-the-work">Survey of the Work</a></li>
        <li><a href="#description-of-existing-similar-systems">Description of Existing Similar Systems</a></li>
      </ul>
    </li>
    <li>
      <a href="#-architecture"> ➤ Architecture</a>
      <ul>
        <li><a href="#phases-description">Phases Description</a></li>
        <li><a href="#use-case-scenario">Use Case Scenario</a></li>
      </ul>
    </li>
    <li>
      <a href="#-datasets"> ➤ Datasets</a>
      <ul>
        <li><a href="#nutrition5k-6">Nutrition 5k</a></li>
        <li><a href="#food101-8">Food 101</a></li>
      </ul>
    </li>
    <li>
      <a href="#-development"> ➤ Development</a>
      <ul>
        <li><a href="#dev-guidelines">General Guidelines & Preprocessing Techniques</a></li>
        <li><a href="#r1-trials--outcomes">R1 Trials & Outcomes</a></li>
        <li><a href="#c1-trials--outcomes">C1 Trials & Outcomes</a></li>
      </ul>
    </li>
    <li>
     <a href="#-testing"> ➤ Testing</a>
     <ul>
        <li><a href="#unit-testing">Unit Testing</a></li>
        <li><a href="#ui-testing">UI Testing</a></li>
      </ul>
    </li>
    <li>
      <a href="#-user-manual"> ➤ User Manual</a>
      <ul>
        <li><a href="#installation-guide"> Installation Guide</a></li>
        <li><a href="#getting-started">Getting Started</a></li>
      </ul>
    </li>
    <li><a href="#-conclusion"> ➤ Conclusion</a></li>
    <li><a href="#-contributors"> ➤ Contributors</a></li>
    <li><a href="#-references"> ➤ References</a></li>
    <li><a href="#%EF%B8%8F-copyrights"> ➤ Copyrights</a></li>
  </ol>
</details>

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<!-- SCIENTIFIC BACKGROUND -->
## 📋 Background

<!-- BACKGROUND: PAPER 1-->
#### <a name="paper-1"></a> Paper 1: Food Detection and Recognition Using CNN <a href="#ref-1"> [1] </a>
&nbsp; &nbsp; &nbsp; &nbsp; The researchers praised the effectiveness of CNNs for food image recognition and detection.
They found out that CNN performed much better than traditional methods using handcrafted features.
Through observation of trained convolution kernels, they confirmed that color features are essential to food image recognition.
The researchers applied CNN to food detection, finding that CNN significantly outperformed a baseline method. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/48348589/187911138-86e5f727-ec84-4ea9-8fcd-85f4411724e0.png"/>
  <br/> 
  <i>Paper CNN Accuracy</i>
</p>

<!-- BACKGROUND: PAPER 2-->
#### <a name="paper-2"></a> Paper 2: Food Recognition - New Dataset, Experiments and Results <a href="#ref-2"> [2] </a>
&nbsp; &nbsp; &nbsp; &nbsp; In the paper, researchers designed a suitable automatic tray analysis pipeline
that takes a tray image as input, finds the regions of interest and predicts for each region the corresponding food class.
The researchers evaluated three different classification strategies using several visual descriptors.
The best performance has been obtained by using ConvolutionalNeural-Networks-based features.
  
<p align="center">
  <img src="https://user-images.githubusercontent.com/48348589/187913657-796354eb-93bb-4b76-a722-b3eb9426aec4.png"/>
  <br/> 
  <i>Paper Food Recognition Results</i>
</p>

<!-- BACKGROUND: PAPER 3-->
#### <a name="paper-3"></a> Paper 3: Deep Learning-Based Food Calorie Estimation Method in Dietary Assessment <a href="#ref-3"> [3] </a>
&nbsp; &nbsp; &nbsp; &nbsp; Their method includes 5 steps: image acquisition, object detection, 
image segmentation volume estimation, and calorie estimation. To estimate calories, it requires the user to take 
a top view and a side view of the food before eating with a smartphone. 
Each image used to estimate must include a calibration object; in their experiments. 
The researchers use the One Yuan coin as a reference. To get better results, they choose to use 
Faster Region-based Convolutional Neural Networks (Faster R-CNN) to detect objects and GrabCut as 
segmentation algorithms. To estimate the volume of each food they used the next equations.

<p align="center">
  <img src="https://user-images.githubusercontent.com/48348589/187931429-a95b6be8-3964-4374-96a5-b9a73794abc2.png"/>
  <br/> 
  <i>Paper Food Volume Equations</i>
</p>

<!-- BACKGROUND: SURVEY-->
#### Survey of the Work
&nbsp; &nbsp; &nbsp; &nbsp; We posted an online Google Form Survey on different social media
apps to provide us with important statistical analysis and most importantly,
how the idea we are on, motivated the common people.

<table>
  <tr>
    <td align="center"><img src="https://user-images.githubusercontent.com/48348589/187936295-e874d3f0-ade7-4c1e-8b08-0116d5154a67.png" width="400px;" </td>
    <td align="center"><img src="https://user-images.githubusercontent.com/48348589/187936323-b59ed851-cd58-4401-8040-6a784fd6ece7.png" width="400px;" </td>
    <td align="center"><img src="https://user-images.githubusercontent.com/48348589/187936340-a8c40425-d26a-47b3-a992-ca0ba90e1c8c.png" width="400px;" </td>
  </tr>
  <tr>
    <td align="center"><img src="https://user-images.githubusercontent.com/48348589/187936351-1d2cb8a9-365b-4454-ad91-4a82a1c2a4b2.png" width="400px;" </td>
    <td align="center"><img src="https://user-images.githubusercontent.com/48348589/187936365-41bd26da-2535-43f1-9f0c-9618ea7460f6.png" width="400px;" </td>
    <td align="center"><img src="https://user-images.githubusercontent.com/48348589/187936375-f61ff62c-382c-49be-9913-59f6795bca4b.png" width="400px;" </td>
  </tr>
</table>

<!-- BACKGROUND: CAREIUM COMPARISON WITH THE EXISTING APPLICATIONS-->
#### Description of Existing Similar Systems
- HealthifyMe <a href="#ref-4"> [4] </a> </br>
&nbsp; &nbsp; &nbsp; &nbsp; A mobile application that provides smart meal plans, Customized
workout plans with certified fitness coaches, and Tracks daily calorie
intake, weight goals, and workouts. Sleep monitoring, meal journal & step
counter. Health advice recipes, and a daily dose of motivation for fitness
goals through fresh content on the app's feed.

- MyFitnessPal <a href="#ref-5"> [5] </a> </br>
&nbsp; &nbsp; &nbsp; &nbsp; A mobile application that gives accurate nutrition facts for over 
14 million foods. Easily log everything eaten to the food diary. Engaged
online community of 200 million members. 250+ healthy recipes. 
150+ workouts keep routines fresh and fun. Logging Food by scanning a barcode.

<p align="center">
  <img src="https://user-images.githubusercontent.com/48348589/187941549-1cebbb9f-ab52-4d8e-9e0e-a3df6326ba44.png"/>
  <br/> 
  <i>Existing Systems Comparison</i>
</p>

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 📐 Architecture
<p align="center">
  <img src="https://user-images.githubusercontent.com/48348589/188155044-6c3dbad7-d879-4765-86c3-099b4c96d1f0.jpg"/>
  <br/> 
  <i>Careium-AI System Architecture</i>
</p>

<!-- ARCHITECTURE: PHASES DESCRIPTION -->
### Phases Description

`Food Detection Model` | `Food Recognition Model` | `Nutrition Extractor Model`
:------: | :------: | :------:
Takes an image as an input and by using Deep Neural Networks, Image Label is resulted whether the image contains food or not. ***(future work)*** | Takes the detected Food Image, pre-process the image and returns the food label based on the most probability gained. | Depends mostly on the user profile (calories & nutrition needs). Based on his behavior a set of proper foods/meals are recommended.
**`Recommendation Model`** | **`Daily Meals Reminder`** | **`Report Generation`**
Depends mostly on the user profile (e.g. calories) Based on his behavior a set of proper foods/meals are recommended. | Periodically reminds the healthy-life seeker with each meal time. | Generates reports according to the statistics and BMR based on user activities.

<!-- ARCHITECTURE: USE CASE SCENARIO -->
### Use Case Scenario

<p align="center">
  <img src="https://user-images.githubusercontent.com/48348589/188158672-352a1f8b-1469-4d81-87f9-060f9055da1b.png"/>
  <br/> 
  <i>Careium-AI Use Case Scenario</i>
</p>

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 💽 Datasets

<!-- DATASETS: NUTRITION5K-->
#### Nutrition5K <a href="#ref-6">[6]</a>
According to Google research datasets <a href="#ref-7">[7]</a>:
 - **Nutrition5k** is a dataset of visual and nutritional data for ~5k realistic plates of food.
 - **Nutrition5k** Scans data for 5,006 plates of food, each containing:
   - 4 rotating side-angle videos
   - Overhead RGB-D images (when available)
   - Fine-grained list of ingredients
   - Per-ingredient mass
   - Total dish mass and calories
   - Fat, protein, and carbohydrate macronutrient masses

<!-- DATASETS: FOOD101-->
#### Food101 <a href="#ref-8">[8]</a>
According to the Food101 paper <a href="#ref-9">[9]</a>,
**Food101** is a dataset of 101,000 real-world images in total:
  - 750 training images
  - 250 testing images
  - the training images were not cleaned, and thus still contain some amount of noise

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 💻 Development 

<!-- DEVELOPMENT: GENERAL GUIDELINES -->
#### <a name="dev-guidelines"></a> General Guidelines & Preprocessing Techniques
- Uses [**Nutrition5k**](#nutrition5k-6) Dataset for Regression
- Uses [**Food101**](#food101-8) Dataset for Classification
- Train-Valid-Test split
  * Train Size => 2771
  * Valid Size => 380
  * Test Size => 360
- Target Size (24x24) and Batch Size (16)
- Training/Evaluation Metric
- Inputs/Outputs Normalization

<!-- DEVELOPMENT: R1 TRIALS -->
#### R1 Trials & Outcomes
|   Model  | Test Loss | Cal Loss | Mass Loss | Fat Loss | Carb Loss | Prot Loss |
|:--------:|:---------:|:--------:|:---------:|:--------:|:---------:|:---------:|
|**1. ML Model**|**`0.8764`**|0.172|0.181|0.173|0.182|0.163|
|**2. Sequential DL Model**|**`0.7613`**|0.143|0.151|0.151|0.163|0.153|
|**3. Pre-trained MobileNet**|**`0.4768`**|0.112|0.094|0.092|0.087|0.091|
|**4. Pre-trained Inception-v3**|**`0.2957`**|0.076|0.064|0.061|0.052|0.042|

<p align="center">
  <img src="https://user-images.githubusercontent.com/48348589/188277950-c7731c31-18d7-440e-93df-bf1228b759f2.jpg"/>
  <br/> 
  <i>Careium-AI R1 Architectures</i>
</p>

<!-- DEVELOPMENT: C1 TRIALS -->
#### C1 Trials & Outcomes
|            | Base Model Accuracy | Optimized Model Accuracy |
|:----------:|:-------------------:|:------------------------:|
|**Training**|        61.23%       |       **`81.34%`**       |
|**Testing** |       [51%-68%]     |       **`78.50%`**       |

<p align="center">
  <img src="https://user-images.githubusercontent.com/48348589/188278329-08c4ddd9-0e96-4ce0-8feb-57d3c39627b8.png"/>
  <br/> 
  <i>Careium-AI C1 Performance</i>
</p>

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 🔌 Testing

#### Unit Testing
we tested the core application pillars by adding unit tests to robust functions in the application.
- A snapshot of a unit test to validate the **login input** <BR>
 ![](https://user-images.githubusercontent.com/48348589/189199093-e728b92d-a4c2-4011-887d-cd5ca9b6c6ca.png)

- A snapshot of another unit test to validate the **register input**
 ![](https://user-images.githubusercontent.com/48348589/189199181-f0f64027-275d-4747-aac2-b2e3bb6ae593.png)

#### UI Testing
we tested the frontend UI by adding UI tests to test the visibility of the screens, text, buttons, and much more. 
![](https://user-images.githubusercontent.com/48348589/189199439-904bfe72-72b7-48fa-9d5f-676e849e3485.png)

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 📖 User Manual 

<!-- USER MANUAL: INSTALLATION -->
### <a name="installation-guide"></a> Installation Guide --> `FOR OPEN SOURCE DEVELOPERS`
- Please refer to the [project's documentation](https://github.com/KAN-Team/Careium-AI/tree/main/zDocumentation) to know more about the project scenario 
- Also, refer to the [CONTRIBUTING.md](https://github.com/KAN-Team/Careium-AI/blob/main/CONTRIBUTING.md) for the purpose of a bug fix or proposing a feature.
- Navigate to the [main/Models](https://github.com/KAN-Team/Careium-AI/tree/main/Models) directory to give a look at the used AI models
- Install [Android Studio](https://developer.android.com/studio) with the **Bumblebee version or higher**
- Sync the [build.gradle-app](https://github.com/KAN-Team/Careium-AI/blob/main/Careium/app/build.gradle) file with `minSDK 28`, `compileSdk 31` or higher making sure of the existence of the additional dependencies below
  ```
  // Drawer Layout
  implementation 'androidx.drawerlayout:drawerlayout:1.1.1'

  // Rounded Image View
  implementation 'com.makeramen:roundedimageview:2.3.0'

  // Bottom Navigation Bar
  implementation 'com.etebarian:meow-bottom-navigation-java:1.2.0'

  // Circular Floating Action Menu
  implementation 'com.oguzdev:CircularFloatingActionMenu:1.0.2'
  implementation 'androidx.legacy:legacy-support-v4:1.0.0'

  //tensorflow
  implementation('org.tensorflow:tensorflow-lite:2.4.0') { changing = true }
  implementation('org.tensorflow:tensorflow-lite-support:0.1.0') { changing = true }
  implementation 'org.tensorflow:tensorflow-lite-metadata:0.1.0'
  implementation 'com.google.firebase:firebase-storage-ktx:20.0.1'
  implementation 'androidx.gridlayout:gridlayout:1.0.0'

  //view model
  def lifecycle_version = "2.1.0"
  //noinspection GradleDependency
  implementation "androidx.lifecycle:lifecycle-extensions:$lifecycle_version"

  //YOYO animation
  implementation 'com.daimajia.androidanimations:library:2.4@aar'

  // Firebase
  implementation 'com.google.firebase:firebase-auth-ktx:21.0.6'
  implementation 'com.google.firebase:firebase-database:20.0.5'

  // Testing
  testImplementation 'junit:junit:4.13.2'
  androidTestImplementation 'androidx.test.ext:junit:1.1.3'
  androidTestImplementation 'androidx.test.espresso:espresso-core:3.4.0'
  testImplementation "com.google.truth:truth:1.1.3"
  androidTestImplementation "com.google.truth:truth:1.1.3"
  androidTestImplementation 'androidx.test:runner:1.4.0'
  androidTestImplementation 'androidx.test:rules:1.4.0'
  androidTestImplementation 'androidx.test:core:1.4.0'
  androidTestImplementation 'androidx.test.ext:junit-ktx:1.1.3'
  ``` 
> For the need of accessing the database server, please, contact one of the [main admins](https://github.com/KAN-Team/Careium-AI/blob/main/CONTRIBUTING.md#question) at once.

<!-- USER MANUAL: STARTING -->
### <a name="getting-started"></a> Getting Started --> `FOR END-USERS GUIDANCE`

- Download the [app-realease.apk](https://drive.google.com/drive/folders/1nRSwTNkt4A0v-eDkRlX9mrywlo5ADhrR)
- Follow the tips below for more guidance on how to use **Careium-AI**
  
  - <B>TIP #1:</B> Make sure that you are connected to the internet

  - <B>TIP #2:</B> On the first screen that appears, you can select if you want to login or register
  
    ![1_](https://user-images.githubusercontent.com/52586356/188292627-6d7a0ac3-83e5-46ed-82d2-e17806633bf2.png)

  - <B>TIP #3:</B> If you click on **Register**, you will need to go through three separate screens to enter your data
    - First Screen: <ins>Name</ins>, <ins>Email</ins>, <ins>Password</ins> and <ins>Confirm Password</ins>
    - Second Screen: <ins>Height</ins>, <ins>Weight</ins>, <ins>Age</ins> and <ins>Gender</ins>
    - Third Screen: <ins>adjust your goals</ins>
    
    ![2_](https://user-images.githubusercontent.com/52586356/188292630-877b3ff0-3238-4fe4-bd2a-666246a6f561.png)

  - <B>TIP #3 (CONT):</B> If you click on **Login**, a screen will appear to enter the previously registered email and password
  
    ![3_](https://user-images.githubusercontent.com/52586356/188292634-ec07c4f0-62f7-4fc4-9fda-1ca3b53c47ec.png)

  - <B>TIP #4:</B> Home screen navigations
    - **Total calories remaining** according to the user's needs (previously determined from his personal desire)
    - **Left/Bottom navigation bar** that enables the user to explore the application features
    - **Floating action button** that enables the user to record an action e.g. (food tracker camera, ...)
    
    ![4_](https://user-images.githubusercontent.com/52586356/188292637-ef6b4d05-1dee-4779-b46a-18abb5b0dbc0.png)

  - <B>TIP #5:</B> Users can make private notes that help them to enhance their diet
  
    ![5_](https://user-images.githubusercontent.com/52586356/188292640-d3f7f281-ae08-4ce1-8bcc-1170ec022498.png)

  - <a name="tip-6"></a><B>TIP #6:</B> Users can make custom alarms to remind them with each meal time
  
    ![6_](https://user-images.githubusercontent.com/52586356/188292646-63845ce4-d362-47f5-9036-4d6d36bd1c41.png)

  - <B>TIP #7:</B> **Careium-AI** provides the user with weekly reports that have detailed information since the last report
  
    ![7_](https://user-images.githubusercontent.com/52586356/188292648-33709587-feeb-4c44-b549-609c81698014.png)

  - <B>TIP #8:</B> The user can track his meal using the app camera to get information
    - The meal name
    - Total meal calories
    - Total meal proteins
    - Total meal fats
    - Total meal carbs
    
    ![8_](https://user-images.githubusercontent.com/52586356/188292652-a3992f42-f5bc-4ed7-aebd-fc3f2b580c4f.png)

  - <B>TIP #9:</B> Careium-AI sotres each meal image in the meal studio
  
    ![9_](https://user-images.githubusercontent.com/52586356/188292654-5bb409bb-39c2-46b6-91c6-af1e836bf9f9.png)

  - <B>TIP #10:</B> The meal notification message received on time selected before [(from tip #6)](#tip-6)
  
    ![10_](https://user-images.githubusercontent.com/52586356/188292659-78141836-fc50-4065-b7a3-91eb52ea1e3a.png)

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

### 💡 Conclusion
<a href="#-conclusion"></a>

&nbsp; &nbsp; &nbsp; &nbsp; Careium AI Food Tracker shows astonishing results compared to what was expected for a simple use case example. Capturing the food plate, long dish, deep dish or even scattered amount of food, Careium can still segment the food region, process it and predicts the main five nutrition components (Calories, Mass, Fat, Carbs, Proteins). Calories are measured in cal, all others are measured in grams. It can be used in classifying a mixed dish of food into multiple food categories, generating food-eaten reports periodically, recommending a proper meal from a set of different available meals in a given dataset and giving alarms for each mealtime.

&nbsp; &nbsp; &nbsp; &nbsp; We provide evidence of the challenging nature of visual annotation in our human portion size
estimation studies, demonstrating the limitations of typical data annotation
approaches in this space. We validate the effectiveness of our approach to data
collection and the resulting **Nutrition5k** <a href="#ref-6">[6]</a> dataset by training a neural network that
can outperform professional nutritionists at caloric and macronutrient estimation in
the generic food setting. We further introduce multiple baseline approaches of
incorporating depth data to significantly improve upon our direct nutritional
prediction from 2D images alone.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

### ✨ Contributors 

Credits and thanks go to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/kareem100"><img src="https://user-images.githubusercontent.com/48348589/187675187-d7b4dfb2-9c21-44a0-94a7-354917eb01ed.png" width="100px;" alt="Kareem Sherif's Image"/><br/><sub><b>Kareem S. Fathy</b></sub></a><br/><a href="https://github.com/KAN-Team/Careium-AI/tree/main/Models" title="Data">🔣</a> <a href="https://github.com/KAN-Team/Careium-AI/commits?author=kareem100" title="Code">💻</a> <a href="https://github.com/KAN-Team/Careium-AI/issues?q=is%3Aissue+author%3AKareem100" title="Bug Reports">🐛</a> <a href="https://github.com/KAN-Team/Careium-AI/issues/assigned/Kareem100" title="Ally">♿️</a> </td>
    <td align="center"><a href="https://github.com/kareem983"><img src="https://user-images.githubusercontent.com/48348589/187675210-25025334-b0bf-4b55-a7ab-ecab0c7881bd.jpg" width="100px;" alt="Kareem Saeed's Image"/><br/><sub><b>Kareem S. Ragab</b></sub></a><br/><a href="https://github.com/KAN-Team/Careium-AI/commits?author=kareem983" title="Code">💻</a> <a href="https://github.com/KAN-Team/Careium-AI/issues?q=is%3Aissue+author%3Akareem983" title="Bug Reports">🐛</a> <a href="https://github.com/KAN-Team/Careium-AI/issues?q=is%3Aissue+assignee%3Akareem983+is%3Aclosed" title="Issues">♿️</a> </td>
    <td align="center"><a href="https://github.com/Abanoub-Asaad"><img src="https://user-images.githubusercontent.com/48348589/187675220-52182d10-901d-4706-ab79-19aec08bcf7c.jpg" width="100px;" alt="Abanoub Asaad's Image"/><br/><sub><b>Abanoub A. Azaab</b></sub></a><br/><a href="https://stackoverflow.com/users/15864740/abanoub-asaad" title="Blogposts">📝</a> <a href="https://askubuntu.com/users/1247223/abanoub-asaad" title="Questions">💬</a>
    <td align="center"><a href="https://github.com/nada-elsayed-anies"><img src="https://user-images.githubusercontent.com/48348589/187675235-a022e96b-48af-4130-8916-d6e4457cb417.jpg" width="100px;" alt="Nada ElSayed's Image"/><br/><sub><b>Nada S. Anies</b></sub></a><br/><a href="https://github.com/KAN-Team/Careium-AI/commits?author=nada-elsayed-anies" title="Code">💻</a> <a href="href="https://github.com/KAN-Team/Careium-AI/issues?q=is%3Aissue+author%3Anada-elsayed-anies" title="Bug reports">🐛</a> <a href="" title="Design">🎨 </td>
    <td align="center"><a href="https://github.com/nada263"><img src="https://user-images.githubusercontent.com/48348589/187675250-ff957956-6bda-42e8-85f9-89bf7c7f8d6a.jpg" width="100px;" alt="Nada Mohamed's Image"/><br/><sub><b>Nada M. Abdelhamed</b></sub></a><br/> <a href="" title="Design">🎨 <a href="" title="Documentation">📖 </td>
  </tr>
</table>

#### A word from our leaders 
> Our hope is that the release of this project will inspire further innovation in the automatic nutritional understanding space and provide a benchmark for the evaluation of future techniques. Download it and enjoy with our release ☺️.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<!-- REFERENCES -->
### 📚 References

##### &nbsp; &nbsp; [1] <a name="ref-1" href="https://dl.acm.org/doi/abs/10.1145/2647868.2654970">Food Detection and Recognition using CNN, Author: Hokuto Kagaya, Nov 22, 2014</a> <i>(Last Accessed on 11-2021)</i>
##### &nbsp; &nbsp; [2] <a name="ref-2" href="https://paperswithcode.com/paper/nu-innet-thai-food-image-recognition-using"> Food Recognition using InNet Model, author: Chakkrit Termritthikun, Aug 01, 2017</a> <i>(Last Accessed on 11-2021)</i>
##### &nbsp; &nbsp; [3] <a name="ref-3" href="https://ieeexplore.ieee.org/document/9397023"> Food Calories Estimation Using Machine Learning, author: Vishakha A. Metre Apr 09, 2021</a> <i>(Last Accessed on 12-2021)</i>
##### &nbsp; &nbsp; [4] <a name="ref-4" href="https://play.google.com/store/apps/details?id=com.healthifyme.basic&hl=en&gl=US">HealthifyMe: related existing application </a> <i>(Last Accessed on 03-2022)</i>
##### &nbsp; &nbsp; [5] <a name="ref-5" href="https://www.myfitnesspal.com/">Myfitnesspal: related existing application </a> <i>(Last Accessed on 05-2022)</i>
##### &nbsp; &nbsp; [6] <a name="ref-6" href="https://github.com/google-research-datasets/Nutrition5k">github.com/google-research-datasets/Nutrition5k</a> <i>(Last Accessed on 04-2022)</i>
##### &nbsp; &nbsp; [7] <a name="ref-7" href="https://github.com/google-research-datasets/">Google researsh datasets</a> <i>(Last Accessed on 04-2022)</i>
##### &nbsp; &nbsp; [8] <a name="ref-8" href="https://www.kaggle.com/dansbecker/food-101">Food 101 | Kaggle.</a> <i>(Last Accessed on 04-2022)</i>
##### &nbsp; &nbsp; [9] <a name="ref-9" href="https://data.vision.ee.ethz.ch/cvl/datasets_extra/food-101/static/bossard_eccv14_food-101.pdf">Food-101 { Mining Discriminative Components with Random...</a> <i>(Last Accessed on 04-2022)</i>
##### &nbsp; &nbsp; [10] <a name="ref-10" href="https://drive.google.com/drive/folders/1nRSwTNkt4A0v-eDkRlX9mrywlo5ADhrR?usp=sharing">Careium APK (app release)</a> <i>(Last Accessed on 07-2022)</i>

<!-- ANOTHER WAY FOR REFERENCES SECTION -->
<!--
<ol>
    <li>
      <a name="ref-1" href="https://dl.acm.org/doi/abs/10.1145/2647868.2654970"> Food Detection and Recognition using Convolution Neural Network, Author: Hokuto Kagaya, Nov 22, 2014</a> <i>(Last Accessed on 11-2021)</i>
    </li>
    <li>
      <a name="ref-2" href="https://dl.acm.org/doi/abs/10.1145/2647868.2654970"> Food Detection and Recognition using Convolution Neural Network, Author: Hokuto Kagaya, Nov 22, 2014</a> <i>(Last Accessed on 11-2021)</i>
    </li>
</ol>
-->

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

### ©️ Copyrights
- [KAN Org.](https://github.com/KAN-Team/)
- [FCIS, University of Ain Shams](https://cis.asu.edu.eg/ar/), Egypt
 
