<script>
  import axios from 'axios';
  export default {
    
    data() {
      return {
        count: 1,
      }
    },

    methods: {
      increment() {
        this.count++
      },
      decrement() {
        this.count--
      },
      async getNumber() {
        const response = await axios.get('http://localhost:3001/');
        console.log(response.data)
      },
    },
   
    mounted() {
      console.log(`The initial count is ${this.count}.`)
    }
  }
  </script>
  
  <template>
  <html>
  <body>
    <button  @click="getNumber">Count is: {{ count }}</button>
    <input id="number"/>
  
    
  </body>
  </html>
  </template>
  