<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Sidebar from "./components/sidebar/Sidebar.vue";
</script>

<template>
  <div class="flex w-full h-full items-center justify-center">
    <div class="flex w-full h-full justify-center flex-col p-2">
      <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

      <div class="sm:flex-row flex flex-col w-full items-center justify-center">
        <button @click="handleLogIn" class="flex w-40 h-11 items-center justify-center border border-gray-300 rounded-lg bg-gray-50 hover:bg-gray-100">
          LogIn
        </button>
      </div>
    </div>

    <Sidebar position-top="0px" />

    <!-- <b-button variant="outline-primary">Button</b-button> -->
    </div>

</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

/* @media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
} */
</style>
