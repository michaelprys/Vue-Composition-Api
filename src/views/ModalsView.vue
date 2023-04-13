<template>
  <div class="modals">
    <h1>Modals</h1>
    <div>
      <label>
        Show dark modals?
        <input v-model="showDarkModals" type="checkbox" />
      </label>
    </div>
    <pre>{{ showDarkModals }}</pre>
    <button @click="showModal = true">Show modal</button>
    <component
      v-model="showModal"
      :is="showDarkModals ? ModalDark : Modal"
      title="My modal title (via prop)"
    >
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis
        nostrum, eum quibusdam harum soluta illum cupiditate culpa aut mollitia
        laboriosam, quod quo fuga quidem amet ipsum dolore consequuntur
        voluptatem dolorem!
      </p></component
    >
  </div>
</template>

<script setup>
/*imports*/
import { ref } from "vue";
import Modal from "../components/Modal.vue";
import ModalDark from "../components/ModalDark.vue";

/*modals*/

const showDarkModals = ref(false);
const showModal = ref(false);
</script>
