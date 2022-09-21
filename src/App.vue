<script setup>
import {  RouterView } from 'vue-router';
// import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <!-- <html> -->
    <header>
      <h1>Vue Project</h1>
      <nav>
        <ul>
          <li><a href="http://127.0.0.1:5173/dashboard" >Dashboard</a></li>
          <li><a href="http://127.0.0.1:5173/login" >Login</a></li>
          <li><a href="http://127.0.0.1:5173/signup" >SignUp</a></li>
        </ul>
      </nav>
    </header>
    
  
  
  
    

  <RouterView />


<!-- </html> -->
</template>

<style scoped>
  
  header {
    background-color: #f1f1f1;
    height: 10vh;
    padding: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 20px;
    color: #4CAF50;
  }
  header > h1 {
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 50px;
    color: #4CAF50;
    margin: 0px
  }
  header > nav {
    height: 03vh;
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 20px;
    color: #4CAF50;
  }
  header > nav > ul {
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 20px;
    color: #4CAF50;
  }
  header > nav > ul > li {
    list-style: none;
    margin: 10px;
  }
  header > nav > ul > li > a {
    text-decoration: none;
    color: #4CAF50;
  }
  header > nav > ul > li > a:hover {
    color: #4CAF50;
    text-decoration: underline;
  }

  nav > a {
    margin: 10px;
  }
  nav > a:hover {
    color: #4CAF50;
    cursor: pointer;
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
   
  


html {
  height: 100vh;
  width: 100vw;
}
</style>
