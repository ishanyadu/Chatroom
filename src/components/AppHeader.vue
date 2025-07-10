<template>
  <nav
    class="w-full bg-gradient-to-r from-blue-400 to-blue-800 text-black px-4 py-5"
  >
    <router-link class="md:hidden" to="/">Home</router-link>
    <router-link
      v-for="item in list"
      :key="item.to"
      class="mx-2 hidden md:inline-block"
      :to="item.to"
      >{{ item.title }}</router-link
    >
    <button v-if="isLoggedIn" class="mx-2" @click="logout">Log  out</button>
    <button v-else class="mx-2" @click="openLogin">
      Login
    </button>
  </nav>
</template>

<script>
import firebase from "../utilities/firebase";
export default {
  data() {
    return {
      list: [
        { title: "Chat", to: "/chat" },
      ],
    };
  },
  computed: {
    isLoggedIn() {
      return this.$store.state.isLoggedIn;
    },
  },
  methods: {
    logout() {
      firebase.auth().signOut();
      // .then((res) => {})
      // .catch((e) => {});
    },
    openLogin() {
      this.$store.commit("setLoginModal", true);
    },
  },
};
</script>

<style></style>
