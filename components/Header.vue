<template>
  <nav class="navbar bg-secondary">
    <div class="container">
      <NuxtLink class="navbar-brand text-light" to="/">SugarFree</NuxtLink>

      <ul class="navbar-nav">
        <li class="nav-item">
          <button
            v-if="isLogged"
            class="btn btn-dark"
            @click.prevent="fakeLogout"
          >
            Выйти
          </button>

          <NuxtLink
            v-else
            class="nav-link text-light"
            to="/login"
          >
            Авторизация
          </NuxtLink>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
import {mapState, mapMutations} from 'vuex';

export default {
  methods: {
    ...mapMutations(['logout']),

    fakeLogout() {
      this.logout()
      this.$router.push('/')
    }
  },

  computed: {
    ...mapState(['isLogged']),
  }
}
</script>
