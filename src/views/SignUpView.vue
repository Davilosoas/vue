<script>
import axios from 'axios';
    
        export default {
        
        data() {
            return {
            count: 1,
            }
        },
        
        methods: {
            async signUp() {
                
                const response = await axios.post('http://localhost:3001/signUp/', {
                username: document.getElementById('username').value,
                password: document.getElementById('password').value,
                email: document.getElementById('email').value
            });
            
            window.location.href = "http://127.0.0.1:5173/login";
            
            },
        },
        
        
        }
</script>
<template>
    
        <html class="signUpHtml" id="signUpBody">
            <div id="signUpTitle">
                <h1>Sign Up</h1>
            </div>
            <div id="signUpForm">
                <div >
                    <label for="username">Username</label>
                    <input type="text" id="username" name="username" placeholder="Username">
                    <label for="email">Email</label>
                    <input type="text" id="email" name="email" placeholder="Email">
                    <label for="password">Password</label>
                    <input type="text" id="password" name="password" placeholder="Password">
                    <!-- <label for="confirmPassword">Confirm Password</label>
                    <input type="text" id="confirmPassword" name="confirmPassword" placeholder="Confirm Password"> -->
                    <button  @click="signUp" class="signUpButton" >Sign Up</button>
                </div>
            </div>
            <footer>
            <p>© 2022 VueProject</p>
            </footer>
        </html>
    
</template>
<style>
    
    #signUpTitle {
        width: 100vw;
        
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 25px;
        color: #4CAF50;
    }
    #signUpBody {
        height: 10vh;
        width: 100vw;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: start;
    }
    #signUpForm {
        width: 100vw;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    #signUpForm div {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    #signUpForm div label {
        font-size: 20px;
        color: #4CAF50;
    }
    #signUpForm div input {
        width: 300px;
        height: 30px;
        margin: 10px;
        border: 1px solid #4CAF50;
        border-radius: 5px;
    }
    
    #signUpBody {
        height: 100vh;
        width: 100vw;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    #signUpForm {
        width: 100vw;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    #signUpForm form input:focus {
        outline: none;
    }
    .signUpButton {
        width: 300px;
        height: 30px;
        margin: 10px;
        border: 1px solid #4CAF50;
        border-radius: 5px;
        background-color: #4CAF50;
        color: white;
        cursor: pointer;
    }	
    .signUpButton:active {
        background-color: white;
        color: #4CAF50;
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
    margin-top: auto;
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
