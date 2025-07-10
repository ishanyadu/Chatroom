<template>
  <div class="flex w-full">
    <div class="m-auto">
      <h1 class="text-center text-2xl md:text-4xl my-2">
        A Simple Login and Chat Web App
      </h1>
      <div class="">
        <div class="flex justify-around mb-4">
        </div>

        <div class="flex justify-center">
          <div class="flex justify-center w-11/12 grid grid-cols-2 md:grid-cols-3 gap-4">
            <div v-for="app in list" :key="app.path" class="text-left my-4">
              <router-link class="w-full" :to="app.path">
                <p class="text-xl font-semibold">🔷 {{ app.title }}</p>
              </router-link>
              <div>
                <div class="font-semibold mt-2">Topic Covered:</div>
                <p v-for="topic in app.concepts" :key="topic">{{ topic }}</p>
              </div>
            </div>
            <div class="text-left my-4">
              <p class="text-xl font-semibold">🔷 Login</p>
              <div class="">
                <div class="text-lg font-semibold">Topic Covered:</div>
                <p v-for="topic in login.concepts" :key="topic">{{ topic }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const list = ref([
      {
        path: "/chat",
        title: "Chat",
        concepts: [
          "- Firebase Realtime Database",
          "- vuex v4",
          "- Custom Router middleware",
        ],
      },
    ]);
    const login = ref({
      title: "Login Modal",
      concepts: [
        "- Create Modal",
        "Vue Custom Events Emitting",
        "Form Handling",
        "firebase authentication",
        "loading effect",
        "Template Refs",
        "component props",
        "firebase google login",
        "Refactoring with component",
        " vue3 teleport",
      ],
    });

    return { list, login };
  },
};
</script>

<style></style>
