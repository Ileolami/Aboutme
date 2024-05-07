---
title: "How to Create Google Login using Google Auth API with React.js"
seoTitle: "Google Login with React: Auth API Guide"
seoDescription: "Learn how to integrate Google login seamlessly into your React.js app using Google Auth API. Simplify user registration with ease"
datePublished: Tue May 07 2024 12:28:49 GMT+0000 (Coordinated Universal Time)
cuid: clvwda8tp000609jrgh6e6voo
slug: how-to-create-google-login-using-google-auth-api-with-reactjs
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1715085162275/a1387925-985f-42f9-9963-c959dee7e4ae.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1715085189415/e5e35c21-2188-4f45-9f59-ae4eb9db7d54.png
tags: web-development, google-cloud, apis, google

---

## Introduction

Before signing up or logging into any account can feel like a thorn in the flesh. There are so many details to input, and sometimes these registration processes can be time-consuming or lead to frustration. But have you ever wondered why this is the case?

To make things easier for users, Google introduced an Auth API to help streamline these lengthy registration processes to be as simple as clicking a button on any application, allowing you to get started right away.

### Brief overview of Google Auth API

What is the Google Auth API? The Google Auth API is a service offered by Google to simplify the registration and login procedures on applications. It enables users to verify their identity by using their Google account details. If you have a Google account(Gmail), the login information you used to make your Gmail account will automatically apply when signing up for any app.

> It is important to note that any app you sign up for by using your Google account automatically has access to your credentials(details).

In this article, you will learn how to create a Google login with Google Auth API.

## Prerequisite

1. knowledge in React.js hooks such `useState`
    
2. A text editor and browser
    
3. Install React using either [Create React app](https://react.dev/) or [Vite](https://vitejs.dev/guide/)
    
4. Know how to use CSS frameworks
    

> The writer will be using Vite And Tailwind CSS

## Required Packages

1. [**React OAuth2 | Google**](https://www.npmjs.com/package/@react-oauth/google#react-oauth2--google)
    
2. [Axios](https://www.npmjs.com/package/axios)
    
3. [Tailwindcss](https://tailwindcss.com/docs/installation/framework-guides) or [Bootstrap](https://getbootstrap.com/)
    
4. [React icon](https://www.npmjs.com/package/react-icons)s
    

## Setting up Google Auth API

### Creating a project in the Google Cloud Console

1. Navigate to [Google Cloud Console](https://console.cloud.google.com/) and Sign up using
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714821019041/a3aa7e9b-2cd7-42be-8fc1-e71ab26e893a.png align="left")
    
2. Click on `APIs & Services` under Quick Access
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714822253324/c98bc81c-a880-485e-94e1-b959229bc2f6.png align="center")
    
3. Click on `NEW PROJECT` to create a new project
    
    2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714821370391/4c0dac99-b478-4d59-8ff7-5be22a51f93f.png align="left")
        
        give it any name of your choice and click on `CREATE`
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714821772192/4d0139bb-6be9-471b-a1af-b2bfe68477e0.png align="left")
        
4. After creating your new project, open the project and click on `OAuth consent screen` on the left-hand side of the page as seen below👇
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714823062502/6c288188-6d8c-4a7e-be26-15261160085d.png align="center")
    
    Click on `External` and `Create` as seen in the picture above 👆
    
5. Add your App information
    
    a. Add your app name and User support Email, you can use your email or your company email.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714823797995/c734fdb4-d932-47b8-a984-af70304a8c66.png align="center")
    
    b. You can add your App logo and App domain including links to privacy policy and term of use if any or ignore it
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714823853342/8fd44415-b249-480f-a0fa-2fb6e6f40381.png align="center")
    
    c. add your developer's contact information and Click on `Save and Continue`
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715012945336/ffdcea01-7972-42ed-a82f-6ee5c40182df.png align="left")
    
6. Ignore the Scope and Click on Save and Continue
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715013429217/044ee48e-0c70-48bf-af64-b23f9b3358d6.png align="left")
    
7. Ignore Test Users and click on `Save and Continue`
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715013659328/01f6cebf-7e6e-4f2b-b835-c0cb03e526b8.png align="left")
    

### Generating OAuth client ID and client secret

After creating your OAuth consent screen, you can now proceed to generate app credentials through these steps.

> Note: Without filling in the details on the OAuth Consent screen, you will not be able to generate credentials for your app.

1. Click on `Credentials` on the left side of your dashboard and click on `+ CREATE CREDENTIALS`
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715013969620/71f58da2-183f-4db6-a417-a78e2f810826.png align="left")
    
2. After clicking on + Create Credentials, you are going to see a popup, select `OAuth client ID`
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715014243787/a48c79ea-f4be-44f9-907d-19aa2af7a3ed.png align="left")
    
3. Select any application type of your choice and add
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715017207841/9d070825-0eb9-4af7-8ffc-60d4d0abf406.png align="left")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715017335426/b623b2b4-b3a2-4b21-a1fd-bbe53566a4c9.png align="left")
    
4. Next, click on ADD URL under `Authorized Javascript Origins` to add your local server port and custom URL
    
    Do the same for `Authorized redirect URLs`
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715017767491/8e55055c-ed5c-4284-b260-0c33a1d99c8c.png align="left")
    
5. Click on Save and you will see a pop-up that displays your client ID and client secretCongratulationson you've successfully generated your Client ID and Client Secret 🎊🎉
    

## Setting up a new project in React.js

### Creating a new project structure

After installing React, clear out the written code `App.jsx/js` to have an empty file like this: 👇

```javascript
import { useState } from 'react'

import './App.css'

function App() {
 
  return (
    <>
      
    </>
  )
}

export default App
```

This is where other components will be displayed. In part two of this lesson, the routing will happen here.

### Installing necessary dependencies

Install all the required packages in your project. using the following command line

1. Axios : `npm i axios`
    
2. React Icons: `npm i react-icons`
    
3. React Oauth Google : `npm i @react-oauth/google`
    

To verify its installation, inspect the `package.json` file to confirm if you have something like this 👇

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714816855958/9e7ed56a-29c8-412c-a26e-f238bfe99c8b.png align="center")

## Implementing Google login in React.js

### Creating an ENV file

1. Create an .env file in your project
    
2. Copy your Client ID from the cloud console under Credential
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715027212666/49b396cd-2f1e-48a8-b5e8-701f730c005f.png align="center")
    
3. Store the ID to the variable
    
    ```javascript
     //FOR vite user
    VITE_CLIENT_ID = //YOUR CLIENT ID 
    
    //for create-react-app user
    
    REACT_APP_CLIENT_ID = //YOUR CLIENT ID
    ```
    

### Wrapping App with Google OAuth Provider

1. Inside your `Main.jsx` or `Index.js` file, Imports the `GoogleOAuthProvider` component from the `@react-oauth/google` library, which helps integrate Google OAuth functionality into your application.
    
    ```javascript
    import { GoogleOAuthProvider } from '@react-oauth/google'
    ```
    
2. wrap your app with the Google OAuth Provider
    
    ```javascript
    <GoogleOAuthProvider clientId={import.meta.env.VITE_CLIENT_ID}>
      {/* Components using Google OAuth */}
      <App />
    </GoogleOAuthProvider>
    ```
    
    * `<GoogleOAuthProvider clientId={import.meta.env.VITE_CLIENT_ID}>`: This line wraps the main application component (`<App />`) with the `GoogleOAuthProvider` component from `@react-oauth/google`.
        
    * `clientId={import.meta.env.VITE_CLIENT_ID}`: This prop provides the Google Client ID for your application stored in `.env` file. However, directly including it here is not recommended due to security concerns.
        

### Creating a Google login button component

1. Created a new file and named it `Login.jsx` under the `src` folder
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1714817785077/95bd8853-57cf-4506-9253-8a13131dccdf.png align="left")

2. Import the following packages to the `Login.jsx`
    
    ```javascript
    import axios from "axios";
    import { useGoogleLogin } from "@react-oauth/google";
    
    import { FcGoogle } from "react-icons/fc";
    ```
    
    `import axios from "axios"` : This line imports the `axios` library, a popular tool for making HTTP requests in JavaScript applications. It allows you to fetch data from APIs or servers.
    
    `import { useGoogleLogin } from "@react-oauth/google`": This line imports the `useGoogleLogin` hook from the `@react-oauth/google` library. This library simplifies integrating Google Sign-In functionality into your React application. The `useGoogleLogin` hook provides a way to trigger Google Sign-In and handle the user's response.
    
    `import { FcGoogle } from "react-icons/fc"` : This line imports the `FcGoogle` component from the `react-icons/fc` library. This library provides access to a collection of icons (including Google) that can be easily integrated into your React components. The `FcGoogle` component specifically renders the Google icon.
    
3. Create a Functional component
    
    ```javascript
    const Login = () => {
      // ... component logic
    };
    ```
    
    This line declares a functional React component named `Login`. Functional components are a way to create reusable UI elements in React by defining a function that returns JSX (JavaScript XML) describing the UI structure.
    
4. Integrate Google login inside the `Login` function
    
    ```javascript
    const login = useGoogleLogin({
      onSuccess: async (response) => {
        try {
          const res = await axios.get(
            "https://www.googleapis.com/oauth2/v3/userinfo",
            {
              headers: { Authorization: `Bearer ${response.access_token}` },
            }
          );
          console.log(res.data);
        } catch (err) {
          console.log(err);
        }
      },
    });
    ```
    
    * This section uses the `useGoogleLogin` hook from the `@react-oauth/google` library.
        
    * It defines a function named `login` that will be triggered by a button click
        
    * Inside the `login` function:
        
        * The `onSuccess` the callback function is defined. This function will be executed if the Google Sign-In process is successful.
            
        * Within the `onSuccess` callback:
            
            * `axios.get` is used to make a GET request to the Google endpoint "[https://www.googleapis.com/oauth2/v3/userinfo](https://www.googleapis.com/oauth2/v3/userinfo)". This endpoint provides information about the logged-in user.
                
            * The request includes an Authorization header with the user's access token retrieved from the `response` object provided by `useGoogleLogin`.
                
            * The response data (user information) is stored in the `res` variable using `await` since the request is asynchronous.
                
            * The `console.log(res.data)` line (for demonstration purposes) logs the user data to the console.
                
                (This will be replaced with logic to utilize the user information in your application (storing it in state)in part two of this tutorial)
                
        * An error-handling mechanism is implemented using a `try...catch` block. If any errors occur during the process, they are caught and logged into the console using `console.log(err)`.
            
5. Button with Google Icon
    
    ```javascript
    return (
      <div className="flex justify-center items-center my-[300px]">
        <button onClick={login} className="flex bg-black rounded-xl">
          <FcGoogle style={{ fontSize: "30px", marginRight: "10px" }} />
          Login with Google
        </button>
      </div>
    );
    ```
    
    This section defines the JSX returned by the `Login` component.
    
    * A `div` element is used as the container. It uses TailwindCSS classes for layout and styling (`flex justify-center items-center my-[300px]`).
        
    * Inside, a button element is created.
        
        * The `onClick` handler of the button is set to the `login` function, triggering the Google Sign-In process when clicked.
            
        * The button styles are defined using a TailwindCSS class (`flex bg-black rounded-xl`).
            
        * The `FcGoogle` component from `react-icons/fc` is used to render the Google icon. Inline styles are applied to adjust the icon size and spacing (`fontSize: "30px", marginRight: "10px"`).
            
        * The button text "Login with Google" is displayed.
            
6. Exporting the Component:
    
    ```javascript
    export default Login;
    ```
    
7. Import the Login component in your App. jsx file to render the component on the screen.
    
    ```javascript
    import Login from './Login'
    
    function App() {
    
      return (
        <>
         <Login />
        </>
      )
    }
    export default App
    ```
    

## Result

1. open your terminal and run the following command
    
    `npm run dev`
    
2. Click on the Localhost to open the local server
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715030723374/662ae3ad-a565-4d9f-8fba-01990637e5d2.png align="left")
    
3. click on the button, sign in by adding your Google account and accept the condition
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715030781322/8e84e24a-b737-4760-885e-c5240d866d97.png align="center")
    
    4. After accepting the condition, go to your browser console to see your Google account details
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715031083168/350ac5b8-1512-4988-91ed-0414dfa57dd7.png align="center")
        
        Remember we log the user data in the console using `console.log(res.data)`
        

## Conclusion

In conclusion, we have successfully implemented Google login using the Google Auth API in React.js. In the upcoming part two of this tutorial, we will utilize the user details obtained during the login process to create a dashboard for the user.

If you find this article helpful, please like, share, subscribe, and follow for more.

You can buy me [a coffee](https://www.buymeacoffee.com/makindemerm).