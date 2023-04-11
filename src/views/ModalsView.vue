<template>
  <div class="modals">
    <h1>Modals</h1>
    <button @click="showModal = true">Show modal</button>
    <teleport to=".modals-container">
      <div class="modal" v-if="showModal">
        <h1>This is a modal</h1>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis
          nostrum, eum quibusdam harum soluta illum cupiditate culpa aut
          mollitia laboriosam, quod quo fuga quidem amet ipsum dolore
          consequuntur voluptatem dolorem!
        </p>
        <button @click="showModal = false">Hide modal</button>
      </div>
    </teleport>
  </div>
</template>

<script setup>
/*imports*/
import { ref } from "vue";
/*modals*/
const showModal = ref(false);
</script>

<style scoped>
.modal {
  background: beige;
  color: black;
  padding: 10px;
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  z-index: 1;
}
</style>
