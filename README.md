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
    git clone https://github.com/tanusree-bose/YOUTUBE-CLONE
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

## How to navigate this project? Click on the link for related source code:

1. Click on different countries in `ChipsBar` will display the most popular videos from that country, by querying the YouTube API. ([click here to view the `Chips` component](https://github.com/1codingguy/react-youtube-clone/blob/main/src/components/ChipsBar/Chips.jsx))

2. Header (Navbar) has different elements in different viewport size:
   ![clone-header](./readme_assets/clone-header.gif) - `HamburgerMenuIcon` is hidden in mobile view. ([click here for `LeftContainer` component for details](https://github.com/1codingguy/react-youtube-clone/blob/main/src/components/Header/LeftContainer/LeftContainer.jsx)) - `SearchBox` is hidden in mobile view, a drawer will appear when clicked on the search icon. And ([Click here to view relevant code](https://github.com/1codingguy/react-youtube-clone/blob/main/src/components/Header/MiddleContainer/MiddleContainer.jsx#L67)) - `SearchPage` has a different YouTube logo in mobile view. There is also a filter button next to the search box (albeit not functional).

3. `HamburgerMenuIcon` has different roles:
   ![sidebar-toggle](./readme_assets/Sidebar-toggle.gif) - In larger screen toggles between mini and full-width sidebar; - in smaller screen opens a drawer. - [Click here for `HamburgerMenuIcon` component](https://github.com/1codingguy/react-youtube-clone/blob/main/src/components/Header/LeftContainer/HamburgerMenuIcon.jsx) - Content of Sidebar is different depends on the screen size. [Click here to show the code that decide what Sidebar to show](https://github.com/1codingguy/react-youtube-clone/blob/main/src/components/Sidebar/SidebarToShow.jsx#L12)

4. A popup menu will appear if clicked on `MoreButton` in each `VideoCard`. [Click here to view `MoreButton` component](https://github.com/1codingguy/react-youtube-clone/blob/main/src/components/Videos/MoreButton.jsx)

5. A search result can be a video or a channel, they have different content and are displayed differently in the SearchPage. [Click here to view the relevant code](https://github.com/1codingguy/react-youtube-clone/blob/main/src/components/Search/ResultsVideoCard.jsx#L64)
   ![search-results](/public/assets/search_results.png)

## Some notable differences between original YouTube and my clone:

1. ChipsBar has no left and right button, and no blur out effect, unlike the original YouTube.
   ![chipsbar-difference](./readme_assets/chipsbar-difference.png)
2. From 1952px, 5 columns of video thumbnails are displayed in the original YouTube. But since material-ui has a 12-column grid layout, there's no way I can have 5 columns since 12/5 is not a whole number.

## Something you should expect when playing with the clone project:

- clicking on a row in any one of the popup menus will merely close the popup menu instead of routing to the another page.
- clicking on most of the buttons won't do anything.

## Why did I build the project this way?

1. Why ChipsBar lists different countries instead of keywords?

   - If using different keywords, clicking on a single chip will perform a search based on that keyword.
   - A search action costs 100 quotas on YouTube API, the daily quota is limited to 5000 for a free account.
   - Querying popular videos from different countries only costs 1 quota.
   - So ChipsBar is designed in this way because of the YouTube API quota.

2. Why use localStorage to save query results from YouTube?

- In the process of development I needed to load the SearchPage again and again, as each search action costs 100 quotas, daily limit quickly runs out.
- Quota was running out once and I had to pause the development process. To avoid such interruption I opted to use localStorage.
- Below picture shows my API quota was quickly used up without using localStorage.
  ![api-quota](./readme_assets/api-quota.png)

## How can you clone and tweak this project?

From your command line, first clone this repo:


Happy coding!

