<template>
  <div>
    <h1>Register</h1>
    <form>
      <input id="username" v-model="username" name="username" type="text" placeholder="username" />
      <br>
      <input id="email" v-model="email" name="email" type="email" placeholder="example@email.com" />
      <br>
      <input id="password" v-model="password" name="password" type="password" placeholder="password" />
      <br>
      <button @click="register">Register</button>
    </form>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  name: 'register',
  data () {
    return {
      username: '',
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
