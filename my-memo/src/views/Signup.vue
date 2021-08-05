<template>
    <div>
        <h1>Signup</h1>
            <input type="text" v-model="userid" placeholder="User ID" />
            <input type="password" v-model="password" placeholder="Password" />
            <button v-on:click="signup">Signup</button>
        <p><i>{{message}}</i></p>
    </div>
</template>

<script>
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
    signup: function (event) {
      this.$http.post('/apis/login', { //axios 사용
        user: this.user
      })
      .then((response) => {
        if (response.data.result === 0) {
          alert('Error, please, try again')
        }
        if (response.data.result === 1) {
          alert('Success')
          this.$router.push('/login') // Login 페이지로 보내줌
        }
      })
      .catch(function (error) {
        alert('error')
      })
    }
  }
}
</script>
