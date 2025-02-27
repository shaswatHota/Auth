# Auth-Service

A full-stack authentication service built with React (Vite) and Firebase for the client side, and Node.js with Express for the server side.

## Features
- User Signup and Login
- Firebase Authentication
- Secure Credential Storage
- Protected Routes
- Redirect after Signup

## Tech Stack
### Client
- React (Vite)
- Firebase Authentication
- Axios for API requests
- React Router

### Server
- Node.js
- Express.js
- Firebase Admin SDK
- CORS Middleware

## Folder Structure
```
Auth-Service/
  ├── client/            # React frontend
  │   ├── src/
  │   │   ├── pages/     # Login, Signup Pages
  │   │   ├── firebaseConfig.js
  │   │   ├── App.jsx
  │   │   ├── main.jsx
  │   ├── public/
  │   ├── package.json
  │   ├── .env
  ├── server/            # Express backend
  │   ├── firebase.js    # Firebase Admin SDK setup
  │   ├── server.js      # Main Express server
  │   ├── routes/
  │   ├── package.json
```

## Setup & Installation
### 1. Clone the Repository
```sh
git clone https://github.com/your-username/auth-service.git
cd auth-service
```

### 2. Set Up the Server
```sh
cd server
npm install
```
- Start the server:
```sh
npm start
```

### 3. Set Up the Client
```sh
cd ../client
npm install
```
- Create a `.env` file in the `client/` directory and add:
```
VITE_FIREBASE_API_KEY=your_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_auth_domain
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_storage_bucket
VITE_FIREBASE_MESSAGING_SENDER_ID=your_messaging_sender_id
VITE_FIREBASE_APP_ID=your_app_id
```
- Start the client:
```sh
npm run dev
```

## API Endpoints
### **Auth Routes**
- **POST** `/signup` - Register a new user.
- **POST** `/login` - Authenticate user.
- **POST** `/verify-token` - Verify user authentication.

## Environment Variables
Ensure the following environment variables are set:
- In **client/.env** (Firebase credentials)

## Firebase Admin JSON (`server/firebase-admin.json`)
This file contains the Firebase service account credentials required for Firebase Admin SDK operations on the server. 
- You need to generate this file from Firebase Console:
  1. Go to **Firebase Console** → **Project Settings**.
  2. Navigate to the **Service accounts** tab.
  3. Click **Generate new private key**, which downloads a JSON file.
  4. Place this JSON file in the `server/` directory as `firebase-admin.json`.

## Troubleshooting
- **Error: Cannot find module './firebase-admin.json'**  
  - Ensure you have downloaded the Firebase Admin JSON file and placed it in `server/`.
- **Network Error on Login**  
  - Ensure the server is running on `http://localhost:3000/`
  - Check CORS settings in `server.js`.
- **Firebase Config Issues**  
  - Double-check the API keys and project IDs in `.env`.
- **Error: DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)**  
  - Ignore it, the Auth will run just fine .

