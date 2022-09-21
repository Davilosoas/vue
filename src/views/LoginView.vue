<script>
import axios from 'axios';
import { setCookie } from "nookies";
    export default {
      
      data() {
        return {
          count: 1,
        }
      },
    
      methods: {
        async auth() {

          

          const response = await axios.post('http://localhost:3001/auth/', {
            username: document.getElementById('user').value,
            password: document.getElementById('psw').value,
          });
          function getToken() {
            const { token, userId } = response.data;
            setCookie(undefined, 'token', token, {
             maxAge: 60 * 60 * 1 
            })
            window.location.href = "http://127.0.0.1:5173/dashboard";
          };

          response.status === 200 ? getToken() : alert('Wrong username or password');  
          
          
            
            
            
           
           
         
          
        },
      },
     
      
    }
</script>
<template>
  <html>
  <body class="aboutBody">
    <div class="loginForm">
      <h1 class="loginTitle">Login</h1>
      <input id="user" class="loginInput" type="text" placeholder="Username" required/>
      <input id="psw" class="loginInput" type="password" placeholder="Password" required/>
      <button class="loginButton" @click="auth"> LOGIN </button>
    </div>
      
  </body>
  <footer>
  <p>© 2022 VueProject</p>
  </footer>
  </html>
</template>

<style>
  .aboutBody {
    background-color: #f1f1f1;
    height: 100vh;
    padding: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 20px;
    color: #4CAF50;
  }
  .loginForm {
    background-color: #f1f1f1;
    height: 50vh;
    width: 50vw;
    padding: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 20px;
    color: #4CAF50;
    flex-direction: column;
  }
  .loginTitle {
    font-size: 50px;
    color: #4CAF50;
  }
  .loginInput {
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    display: inline-block;
    border: 1px solid #ccc;
    box-sizing: border-box;
  }
  .loginButton {
    background-color: #4CAF50;
    color: white;
    padding: 14px 20px;
    margin: 8px 0;
    border: none;
    cursor: pointer;
    width: 100%;
  }
  .loginButton:hover {
    opacity: 0.8;
  }
  footer {
    background-color: #f1f1f1;
    height: 10vh;
    padding: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 20px;
    color: #4CAF50;
  }
  footer > p {
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 20px;
    color: #4CAF50;
  }
</style>
