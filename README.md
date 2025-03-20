# YouTube_clone
 
# YouTube Clone (MERN Stack)

This project is a YouTube Clone built using the **MERN Stack** (MongoDB, Express, React, Node.js). It allows users to upload videos, watch videos, and interact with the content, similar to YouTube.

## Table of Contents

- [Project Setup](#project-setup)
  - [Backend Setup](#backend-setup)
  - [Frontend Setup](#frontend-setup)
- [Features](#features)
- [Technologies](#technologies)
- [Folder Structure](#folder-structure)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [License](#license)

## Project Setup

### Backend Setup

1. **Clone the repository:**
   ```bash
    git clone 
    cd YouTube_Clone

    
   cd Backend
   cd ./server
   npm install
   npm start

  2. **Frontend Setup**

    cd Frontend
    cd ./client
    npm install
3. **Running the Application**

    - Start the backend server
        npm start

    - Start the frontend application
        npm run dev



    /youtube-clone
   
  /backend
  
    /models           # MongoDB models (e.g., User, Video, Comment) 🧳
    /routes           # API routes (e.g., authRoutes.js, videoRoutes.js) 📍
    /controllers      # Business logic for API routes 🧠
    /middlewares      # Middleware (e.g., authentication check) 🛡️
    /config           # Configuration files (e.g., database connection) ⚙️
    server.js         # Backend entry point 🌟
    .env              # Environment variables 🌳
  /frontend
  
    /src
      /components     # React components (e.g., Navbar, VideoPlayer) 🧩
      /pages          # Pages (e.g., HomePage, UploadPage) 📃
      /services       # API services for backend interaction 🖧
      /App.js         # Main React app file 🖥️
      /index.js       # Entry point for React 💻
    package.json      # Frontend dependencies 📜
    .env              # Frontend environment variables 🌐
    
  package.json        # Root package.json for managing dependencies 📦
  
  README.md           # Project documentation 📖

**Environment Variables Create a .env file in the backend directory with the following variables:**
MongoDB_URL="mongodb://localhost:27017/YoutubeClone"                 # MongoDB connection string 🌱
Jwt_secret_key="MySecretKey123"                                      # JWT Secret Key 🔐
PORT=3000                                                            # Port number for the backend server 🌐



## Purpose of the Project 🎯

The **YouTube Clone** project is designed to replicate the core features of YouTube, using the **MERN stack** (MongoDB, Express, React, Node.js). The primary purpose of this project is to:

- **Learn and Practice the MERN Stack**: This project serves as a hands-on learning experience for mastering modern web development using MongoDB, Express, React, and Node.js. By building a full-stack application, you will gain practical knowledge of how to work with databases, manage authentication, and build interactive UIs.
  
- **Video Streaming Platform**: The clone aims to create a basic yet functional video streaming platform where users can upload, watch, and interact with videos. This helps to understand how media handling works in web development and how to integrate video uploading, playback, and commenting features into a website.
  
- **Building Real-World Applications**: The project is designed to simulate real-world web development, where a user-friendly frontend interacts with a robust backend, and both parts work together to create a seamless user experience.
  
- **Focus on User Authentication & Authorization**: Implementing JWT (JSON Web Tokens) for secure user authentication and authorization is a key focus. This feature is essential for handling sign-ups, logins, and maintaining sessions, mimicking how popular platforms like YouTube secure their users.
  
- **Explore Full-Stack Development**: By combining backend technologies (Node.js, Express) with frontend frameworks (React), this project provides a full-stack development experience. It covers everything from setting up an API to connecting the frontend with the backend.

Overall, the **YouTube Clone** project is an excellent opportunity to explore key web development concepts while building a practical application with interactive features similar to popular video streaming platforms. 🌟


