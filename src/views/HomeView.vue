<template>
  <div class="home">
    <h2>{{ appTitle }}</h2>
    <h3>{{ counterData.title }}:</h3>

    <div>
      <button @click="decreaseCounter(2)" class="btn">--</button>
      <button @click="decreaseCounter(1)" class="btn">-</button>

      <span class="counter">{{ counterData.count }}</span>
      <button @click="increaseCounter(1, $event)" class="btn">+</button>
      <button @click="increaseCounter(2)" class="btn">++</button>
    </div>

    <p>This counter is {{ oddOrEven }}</p>

    <div class="edit">
      <h4>Edit counter title:</h4>
      <input v-model="counterData.title" type="text" v-autofocus />
    </div>
  </div>
</template>

<script setup>
import { reactive, computed, watch, onMounted } from "vue";
import { vAutofocus } from "../directives/vAutofocus";

const appTitle = "My Amazing Counter App";

onMounted(() => {
  console.log("Do stuff related to App Title");
});

const counterData = reactive({
  count: 0,
  title: "My Counter",
});

watch(
  () => counterData.count,
  (newCount) => {
    if (newCount === 20) {
      alert("You made it to 20!");
    }
  }
);

const oddOrEven = computed(() => {
  if (counterData.count % 2 === 0) return "even";
  return "odd";
});

const increaseCounter = (amount, e) => {
  counterData.count += amount;
};
const decreaseCounter = (amount) => {
  counterData.count -= amount;
};
onMounted(() => {
  console.log("Do stuff related to Counter");
});
</script>

<!-- <script>
export default {
  data() {
    return {
      count: 0,
    };
  },
  computed: {
    myComputedProperty() {
      // perform some logic based on a data property
      return "my result";
    },
  },
  watch: {
    count(newCount, oldCount) {
      if (newCount == 20) alert("asfadfsas");
    },
  },
  mounted() {
    // do stuff when component is loaded
    console.log("mounted");
  },
  unmounted() {
    // do stuff when component is unloaded from the browser
    console.log("unmounted");
  },
  directives: {
    autofocus: {
      mounted(el) {
        el.focus();
      },
    },
  },
};
</script> -->

<style scoped>
.home {
  text-align: center;
  padding: 20px;
}

.btn,
.counter {
  font-size: 40px;
  margin: 10px;
}
.edit {
  margin-top: 60px;
}
</style>
