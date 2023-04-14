<template>
  <div class="about">
    <h1>Posts</h1>
    <ul>
      <li v-for="post in posts" :key="post.id">
        <router-link :to="`/postDetail/${post.id}`">{{
          post.title
        }}</router-link>
      </li>
    </ul>
    <textarea v-autofocus />
    <button
      @click="counter.increaseCounter(1)"
      :class="{ yellow: counter.oddOrEven === 'odd' }"
      class="counter-button"
    >
      {{ counter.count }}
    </button>
    <div></div>
  </div>
</template>

<script setup>
/*imports*/
import { ref } from "vue";
import { useCounterStore } from "@/stores/counter.js";
import { vAutofocus } from "../directives/vAutofocus";

/*store*/
const counter = useCounterStore();
/*posts*/
const posts = ref([
  {
    id: "id1",
    title: "Post 1",
  },
  {
    id: "id2",
    title: "Post 2",
  },
  {
    id: "id3",
    title: "Post 3",
  },
]);

/*counter button*/
</script>

<style scoped>
ul {
  margin-bottom: 30px;
}
.counter-button {
  font-size: 60px;
  width: 100%;
  background-color: pink;
}

.yellow {
  background-color: yellow;
}
</style>
