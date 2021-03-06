# Smart-Trash-Bin

Reward system based smart trash bin for plastic bottles which helps people economically and at the same time reduce the environment pollution caused by the plastic wastes.

## Description

Users/Customers can dispose used plastic bottles to this smart trash bin and they will be rewarded by some points which they can use them later for many cases. There is a website that users/customers needs to register before disposing bottles to trashbin. All the disposing details will be recorded in a database which users can view them throgh their registered account. In addition to that garbage collectors can also login to their accounts and check the level of trash in the trash bin.

This project is an IOT based project. Now I'll go through the technologies I used.

  ### Web Application
  
  ***Front-End***
  - React with typescript - Most familiar javascript framework
  - Redux and Local storage - To manage complex states
  - Apollo Client with GraphQL - To fetch data from the database
  
  ***Back-End***
  - MongoDb with mongoose - No SQL database
  - GraphQL - GraphQL API instead of REST API
  - JWT Web Tolken - User Authentication
  - Apollo Server - Complex state and cache management for both the frontend and the backend
  - Nodejs with Express
  
I created the wireframes for the website using figma. You can check them [here](https://www.figma.com/file/Nvads7OF32cg0Pa9lUQy2Q/Untitled?node-id=4%3A26). But later I did some changes when developing the website.

GIT REPOS :arrow_right: [Front-End](https://github.com/kaveesh680/Smart-Trash-Bin-FrontEnd.git) [Back-End](https://github.com/kaveesh680/STB-Backend)

<h5 align="center">Sign Up UI - Desktop</h5>
<img src="https://user-images.githubusercontent.com/63943539/139460073-301aea9b-0ee9-4fe1-982f-5fe503d5db19.png">
<h5 align="center">Sign Up UI - Mobile</h5>
<img src="https://user-images.githubusercontent.com/63943539/139461714-bc0c6154-a681-485f-8e0b-c155290ccb90.png">
<h5 align="center">Sign In UI - Desktop</h5>
<img src="https://user-images.githubusercontent.com/63943539/139461931-3c00362b-92f8-4eb9-994e-822de0784b6d.png">
<h5 align="center">Sign In UI - Mobile</h5>
<img src="https://user-images.githubusercontent.com/63943539/139462235-849c7754-3dc6-446e-ba4f-fc3f205087df.png">
<h5 align="center">User HomePage UI - Desktop</h5>
<img src="https://user-images.githubusercontent.com/63943539/139462308-0c15818d-5392-47ce-bf89-ebd2b7ee32ac.png">
<h5 align="center">User HomePage UI - Mobile</h5>
<img src="https://user-images.githubusercontent.com/63943539/139462340-8aeb7d87-ad5e-4a06-a415-0ab39000b89f.png">
<h5 align="center">Garbage Collector Homepage UI - Desktop</h5>
<img src="https://user-images.githubusercontent.com/63943539/139462358-a0f54991-99ca-4f81-81dc-2b13c0419b93.png">
<h5 align="center">Garbage Collector Homepage UI - Mobile</h5>
<img src="https://user-images.githubusercontent.com/63943539/139462373-e58311e3-0213-4297-a14f-69726990b006.png">



## Final Demonstration

For a node I have used following parts
- Microcontroller - RaspberryPi
- 16X4 display
- raspberrypi camera module
- USB camera

For the display first I used Nokia 5110 LCD display. But unkowingly I gave it 5v power instead of 3.3v. So the display was damaged. I couldn't find the same display. So I purchased 16X4 display. 

<p align="center">
<img align="center" src="https://user-images.githubusercontent.com/63943539/140652485-9e1ed98d-31c8-4ffc-9eba-5a650d1c377d.jpeg" width="400" height="400">
  </p>
<h5 align="center">Raspberry Pi</h5>
<p align="center">
<img align="center" src="https://user-images.githubusercontent.com/63943539/140652495-e355e74f-9ced-40fb-b537-386ab25a01a6.jpeg" width="400" height="400">
  </p>
<h5 align="center">USB Camera</h5>
<p align="center">
<img align="center" src="https://user-images.githubusercontent.com/63943539/140652500-fff536ef-8225-47a9-ad87-66a6c92731ef.jpeg" width="400" height="400">
  </p>
<h5 align="center">16X4 Display</h5>
<p align="center">
<img align="center" src="https://user-images.githubusercontent.com/63943539/140652507-26b14d68-89c4-4261-b42d-00dcf1fb42e6.jpeg" width="400" height="400">
  </p>
<h5 align="center">Raspberry Pi Camera</h5>

### Bottle Detection Model

I used following libraries to train the model
- Numpy is used to manipulate array data
- Matplotlib is used to visualize the images and to show how discernable a color is in a particular range of colors
- OS is used to access the file structure
- CV2 is used to read the images and convert them into different color schemes
- Keras is used for the actual Neural Network

I managed to implement the neural network with 100% accuracy and 98% validation accuracy. You can see the dataset I used [here](https://github.com/kaveesh680/bottles.git).In the neural network there is an image processing part. I used a USB camera to capture the image of the bottle then that image goes through image processing algorithm. For the image processing algorithm, I used canny edge algorithm.

I also want  to mention the challenges I faced implementing this model. My initial idea was to train the model to detect bottles according to their sizes. But I struggled with the dataset. So I decided to train the model to detect only the  object is a bottle or not. Still I had the dataset problem. For the dataset first I took about 200 images using my phone and trained the model but prediction didn't work well. Next I got a dataset from a website and again trained the model for that dataset. It also didn't work well. Finally I made my own dataset downloading images from the google one by one. I dowloaded about 300 - 400 images and repeat the same images with different brightness and contrast levels. 
<p align="center">
<img src="https://user-images.githubusercontent.com/63943539/140744713-6e5e4cc8-7ca9-4453-829a-a64a8773a165.png" width="800" height="600">
</p>
<p align="center">
<img src="https://user-images.githubusercontent.com/63943539/140749343-20b5aed0-0d65-4fd3-b45f-1fc4efab674f.jpg" width="400" height="400">
  </p>
<h5 align="center">Image before preprocessing</h5>

<p align="center">
<img src="https://user-images.githubusercontent.com/63943539/141247440-f8e521d9-acdb-48f1-a68c-a6bdb42ec77c.png" width="400" height="400">
  <p align="center">
<h5 align="center">Image after preprocessing</h5>

### QR Code Reading

For the QR code reading, First i tried using ESP32 Module with ESP32 camera. But It worked only the first day. After few days i again tried to check it but didn't work. i tried reuploding the code but result was the same. So then i decided to use raspberry pi camera for QR code reading because it's the embedded camera for the raspberry pi and also resolution and the quality is high comparing to USB camera i have. From the QR code i get 2 credentials of the user, user name and the user id. 

- user name - To show the greeting on the display
- user ID - To update the database with dispose data

<img src="https://user-images.githubusercontent.com/63943539/141252513-7e086e74-58c3-49b3-94d1-6617fc2c8753.jpeg" width="400" height="400">
