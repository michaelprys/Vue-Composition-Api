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
      @click="increaseCounter(1)"
      :class="{ yellow: oddOrEven === 'odd' }"
      class="counter-button"
    >
      {{ counterData.count }}
    </button>
    <div></div>
  </div>
</template>

<script setup>
/*imports*/
import { ref } from "vue";
import { useCounter } from "@/use/useCounter";
import { vAutofocus } from "../directives/vAutofocus";
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
const { counterData, increaseCounter, oddOrEven } = useCounter();
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
