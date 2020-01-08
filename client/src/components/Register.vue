<template>
  <div>
    <h1>Register</h1>
    <form @submit="register">
      <input type="text" placeholder="Name" v-model="name" />
      <br />
      <input type="email" required v-model="email" />
      <br />
      <input type="password" required v-model="password" />
      <br />
      <button type="submit">Submit</button>
    </form>
  </div>
</template>
<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  data () {
    return {
      name: '',
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
        const response = await AuthenticationService.register ({
            email:this.email,
            password: this.password
            })
            console.log(response.data);
    }
  },
  mounted () {}
}
</script>
<style>
</style>

