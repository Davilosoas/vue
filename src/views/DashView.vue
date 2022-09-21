<script>
    import axios from 'axios';
    import { parseCookies } from "nookies";
    
    const getUser = await axios.post('http://localhost:3001/getUser/', {
        token: parseCookies().token,
        });
        
    
    
    const getUsers = await axios.get('http://localhost:3001/getUsers/');
        
        
        

    export default {
      
      data() {
        return {
          users: getUsers.data,
          loggedUser: getUser.data   
        }
      },
    
      methods: {
        async deleteUser(id) {
            const response = await axios.post('http://localhost:3001/deleteUser/', {
                id: id,
                });
                this.users = response.data
                window.location.href = "http://127.0.0.1:5173/dashboard";
        
        }
        
      },
     
      mounted() {
        getUser();
      }
    }
</script>
<template>
    <html>
        <body id="userListBody">
            <div id="userListTitle" >
                <h1> User List </h1>
            </div>
            <div id="userListTable">
                <table>
                    <tr>
                        <th>Username</th>
                        <th>Email</th>
                        <th>Role</th>
                        <th>Actions</th>
                    </tr>
                    <tr v-for="user in users" :key="user.id" >
                        <td>{{ user.username }}</td>
                        <td>{{ user.email }}</td>
                        <td>{{ user.id }}</td>
                        <td>
                            <button class="delBtn" @click="deleteUser(user.id)">Delete</button>
                            
                        </td>
                    </tr>
                </table>
            </div>
        </body>
        

    </html>
    
        
</template>
<style>
    #userListTitle {
        width: 100vw;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 50px;
        color: #4CAF50;
    }
    #userListBody {
        height: 100vh;
        width: 100vw;
        display: flex;
        flex-direction: column;
        /* justify-content: center; */
        align-items: center;
    }
    #userListTable {
        margin-top: 5vh;
    }
    #userListTable > table {
        border-collapse: collapse;
        width: 80vw;
    }
    #userListTable > table > tr > th {
        border: 1px solid black;
        padding: 15px;
    }
    #userListTable > table > tr > td {
        border: 1px solid black;
        padding: 15px;
    }
    .delBtn {
        width: 100px;
        height: 40px;
        border-radius: 5px;
        border: 1px solid #af4c4c;
        background-color: #af4c4c;
        color: white;
        font-size: 20px;
        cursor: pointer;
    }
    .delBtn:hover {
        background-color: #8e463e;
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
