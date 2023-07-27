<template>
  <div class="card p-4 w-25">
    <form>
      <div class="mb-3">
        <label for="login" class="form-label">Login</label>
        <input v-model="username" type="text" class="form-control" id="login" required>
      </div>
      <div class="mb-3">
        <label for="password" class="form-label">Password</label>
        <input v-model="password" type="password" class="form-control" id="password" required>
      </div>
      <button @click.prevent="fakeLogin" class="btn btn-primary">Submit</button>
    </form>
  </div>
</template>

<script>
import { mapMutations  } from 'vuex';

export default {
  data() {
    return {
      username: '',
      password: '',
    }
  },

  methods: {
    ...mapMutations(['login']),

    fakeLogin() {
      if (this.username === 'admin' && this.password === 'password') {
        this.login();
        this.$router.push({name: 'main'})
      }
    }
  }
}
</script>

<style scoped>

</style>
