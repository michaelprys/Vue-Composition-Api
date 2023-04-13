<template>
  <teleport to=".modals-container">
    <div class="modal" v-if="modelValue">
      <h1>{{ title }}</h1>
      <slot />
      <button @click="$emit('update:modelValue', false)">Hide modal</button>
      <div>Username is: {{ userData.username }}</div>
    </div>
  </teleport>
</template>

<script setup>
/*imports*/
import { inject } from "vue";

const userData = inject("userData");

/*props*/
const props = defineProps({
  modelValue: {
    type: Boolean,
    default: false,
  },
});
console.log(props.title);

/*emits*/
const emit = defineEmits(["update:ModelValue"]);
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
