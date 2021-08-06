<template>
    <div>
        <h1>Signup</h1>
            <input type="text" v-model="userid" placeholder="User ID" />
            <input type="password" v-model="password" placeholder="Password" />
            <button @click="registerButton">Signup</button>
        <p><i>{{message}}</i></p>
    </div>
</template>

<script>
import axios from 'axios';
export default{
    name: 'Signup',
    data(){
        return {
            userid:'',
            password:'',
            message:''
        }
    },
    methods: {
      registerButton() {
        const data = {
          'userid' : this.userid,
          'password' : this.password
        };

        axios.post('/api/users', data)
        .then(response => {
          console.log(response.status);
          alert('register successful');
          this.$router.push('/');
        })
        .catch(error => {
          console.log(error);
          console.log('register failed');
          this.message='register failed';
        })
      }
    }
}
</script>
