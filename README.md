##  AI Audio Transcriber 🎙️➡️📜

## 📌 Project Overview
The **AI Audio Transcriber** is a full-stack application that allows users to upload audio files (MP3) and get transcriptions using **OpenAI's API**. The project is built with **Spring Boot (Backend)** and **Vite + React + Vanilla JS (Frontend)**.

## ✨ Features
- 🎵 Upload an MP3 file
- 🤖 AI-powered transcription using OpenAI API
- 🚀 Fast processing with Spring Boot backend
- 🎨 Modern and responsive UI using React + Vite
- 📂 Simple file handling and API integration

## 🛠 Tech Stack
- **Backend**: Spring Boot, Java, OpenAI API
- **Frontend**: React, Vite, Vanilla JavaScript, CSS
- **Others**: Axios, Bootstrap, REST APIs

## 📂 Project Structure
```
AI-Audio-Transcriber/
│── backend/audio-transcribe                # Spring Boot application
│   ├── src/main/java/com/transcriber/
│   │   ├── controllers/    # API Controllers
│   │   ├── services/       # Business Logic
│   │   ├── config/         # OpenAI API Integration
│   │   ├── Application.java
│   ├── pom.xml             # Dependencies (Spring Boot, OpenAI, etc.)
│
│── frontend/ audio-transcribe-frontend              # Vite + React Frontend
│   ├── src/
│   │   ├── components/     # React Components
│   │   ├── App.js          # Main App Component
│   │   ├── index.js        # Entry Point
│   ├── package.json        # Frontend Dependencies
│
│── README.md               # Documentation
```
![image](https://github.com/user-attachments/assets/01611423-8a32-464c-8de1-7c8de4dcadc0)


## 🔧 Setup Instructions
### Step 1: Clone the Repository
```bash

git clone https://github.com/dwivedikirtiman/AI-Audio-Transcriber.git

```

Locate the project folder

```
cd AI-Audio-Transcriber
```

### Step 2: Backend Setup (Spring Boot)

1. Open the **`audio-transcribe`** folder in under the root folder of the project named as **`AI-Audio-Transcribe`** in IntelliJ IDEA with all the required dependencies, it's better to choose ```pom.xml``` file for opeining so that the IDE will automatically install all the important dependencties and the resources required for your application in order to run properly.

2. Make sure your `application.properties` is properly configured:
```properties

spring.application.name=audio-transcribe
spring.ai.openai.api-key=${OPENAI_API_KEY}
spring.ai.openai.audio.transcription.base-url=https://api.openai.com
spring.ai.openai.audio.transcription.options.model=whisper-1
spring.ai.openai.audio.transcription.options.response-format=json

```
**IMPORTANT NOTE** 

-  Make sure to edit the configuration setting of your IDE and adding your actual API_KEY under the environment variable place like this :

  ![image](https://github.com/user-attachments/assets/8dbfd8b5-7d96-4a81-b040-9ea77ea7da68)


After adding your API_KEY click on "Apply" and then click on "OK" Button.

3. Look for all the required java file in the backend application and if there is no error then you're good to go further.
  
4. Run the `AudioTranscribeApplication.java` class to start the backend server.

5. Now, that the server is running fine and all the file is now set-up properly, you need to test your API in POSTMAN that whether it is giving the proper response by hitting the provided URL/URI, for that open your POSTMAN Application and create a new collection with any prefered name and then add the base URL where you're routing the application in order to getting the response, in this case the base route path which is set as ```http://8080/api/transcribe``` and this should be entered as a **POST** request in your POSTMAN, finally the page will look something like this after hitting the send button if all thing is working fine then :

 ![image](https://github.com/user-attachments/assets/f32cbb83-4328-428a-b320-e1bc4c86b98e)

So, from the above picture it is very much clear that in POSTMAN you've to set the base route and in body section 

 ![image](https://github.com/user-attachments/assets/371dbd69-4f77-4f47-9248-cd11bc65defd)

Now, the question is from where I've got the ```test.mp3``` file so this is basically a very light weight mp3 file which has some texts in it, as my API_KEY is of free tier, it will not process some kind of song or any other big file otherwise there will be an error regarding the pricing and we have to pay that much amount to the OPEN AI for using their service.
so for generating this kind of file I've used one website named as <a href = "https://ttsmp3.com/">ttsmp3</a> You can also visit this website for cration of some random mp3 files or you can also use your prefered way to include the mp3 file, only condtion is if you've not sufficient credit in your OPEN AI account then you will need to pay as per your request length

 ![image](https://github.com/user-attachments/assets/8f14e356-62b6-4f1d-9886-e409b19ee552)

So, now we've the test.mp3 file now we have to select that in the POSTMAN file location and hitting the SEND button to send a POST request and need to check whether the request is getting transcribe, if all the things is working fine then the result should be displayed in the POSTMAN same like this, i've highlighted all the major requirements in this pic also as follows:

 ![image](https://github.com/user-attachments/assets/c70250ea-c40e-42bd-9d5f-a87b2a92e853)


### Step 3: Font-End Setup (Vite + React)

- So for running the Front-End setup one thing which should be installed in your system is Node.js before running this front-end part so open the front-end part of the application named as ```audio-transcribe-frontend``` which will be under the root folder named as ```AI-Audio-Transcribe``` in VS code editor as it will be easy to install or run any command or you can also use your system **`CMD`** to run the server before that install the dependencies as I've used **`VITE`** tool to create the front end, this is basically a build tool for front end that can be used for fast development of frontend, nothing fancy here.

so open the front-end part in VS code or in CMD and run the follwoing command one by one

```
npm install   //to install the required dependencies if something is missing

npm run dev     //these both commands should be executed in the front end directory then only it will start the server

```

- If you're wondering what is the steps which i've followed to created the front-end from starting then i'm going to include follwing pics for your reference as it will give you guys an idea as how to create a front end project using VITE tool, but again saying this is only for reference, if you've downloded the source code then you don't need to do it from starting as all the required resources are there in the downloaded project directory
  

 ![Screenshot (104)](https://github.com/user-attachments/assets/8a16a56b-8835-45e1-94d3-813b9dcaa23f)


 ![Screenshot (105)](https://github.com/user-attachments/assets/4f4a6031-b518-476e-b05b-938e7e893aec)

So, from the above pics the steps is pretty much clear but still i'm writing the steps below for reference purpose-

- Firstly open the cmd or even terminal of VS code and run the Vite project creation command as follows:

  ```
   npm create vite@latest
  ```
- after that it will give you an option to name the project which in my case i've give the name as ```audio-transcribe-frontend``` and after that it will ask to choose the framwork in my case that is ```React``` here and after that it will ask to choose the programming language which is ```Javascript``` here so after that it will create the project with the said tech stack and will ask to run you the follwing three commands one by one :

  ```
   cd audio-transcribe-frontend    //to enter in the newly created front end project

   npm install               // to install all the required dependencies for this project

   npm run dev               // to run the front end
  ```

## Important Note- The frontend will be available at ```http://localhost:5173``` 

## 🔗 API Usage
- **POST** `http://localhost:8080/api/transcribe`
- **Request**: Upload an MP3 file
- **Response**: JSON with transcribed text


## 📸 Screenshots & UI Preview

![Screenshot (109)](https://github.com/user-attachments/assets/1eee4eee-5b9e-4710-8607-08d789a238ec)

after clicking on the Transcribe Button as the test file has been already choosed as shown in the above pic, now we want to transcribe the content fron that test.mp3 file the result is as follows: 

![image](https://github.com/user-attachments/assets/75dafd40-f2c9-4a4f-9435-8d2f66369b95)


## ⚙️ How It Works

1️⃣ User uploads an MP3 file 📂

2️⃣ File is sent to the Spring Boot backend 🚀

3️⃣ OpenAI API processes the audio 🤖 

4️⃣ Transcribed text is returned and displayed on UI 🎉

## 🚀 Future Enhancements(Optional/Suggestions)

- 🎙️ Support for multiple audio formats
  
- 🌎 Multi-language transcription
  
- 📄 Export transcriptions as PDF

## ⚙️ Contribution
Contributions are welcome! Feel free to raise issues or submit pull requests to improve the project.

## 📜 License
This project is open-source. Feel free to use and modify it!

## 👨‍💻 Author

**[Kirtiman Dwivedi]**

GitHub: https://github.com/dwivedikirtiman

Linkedin: https://www.linkedin.com/in/kirtiman-dwivedi/

Email: [dwivedikirtiman000@gmail.com]

Let’s connect—I’d love to hear your feedback! 🚀

