<template>
  <div>
    <h1>Register</h1>

    <input 
      type="email"
      name="email"
      v-model="email" 
      placeholder="email" />
    <br>
    <input 
      type="password"
      name="password"
      v-model="password"
      placeholder="passwords" />  
    <br>
    <Button
      @click="register">Registeer</button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  data () {
    return {
      email: '123',
      password: 'abc'
    }
  },
  methods: {
    async register () {
      await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
    }
  }
}
</script>

<style scoped>

</style>
