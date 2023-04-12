<template>
  <div class="modals">
    <h1>Modals</h1>
    <button @click="showModal = true">Show modal</button>
    <Modal v-if="showModal">
      <template #title>My new title</template>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis
        nostrum, eum quibusdam harum soluta illum cupiditate culpa aut mollitia
        laboriosam, quod quo fuga quidem amet ipsum dolore consequuntur
        voluptatem dolorem!
      </p></Modal
    >
  </div>
</template>

<script setup>
/*imports*/
import { ref } from "vue";
import Modal from "../components/Modal.vue";
/*modals*/
const showModal = ref(false);
</script>
