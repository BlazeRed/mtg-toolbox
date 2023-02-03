<template>
  <div class="container">
    <div
      class="row no-wrap justify-center items-center"
      style="position: relative"
    >
      <q-btn v-touch-repeat.mouse="decrement" class="btn left" flat
        ><p>-</p></q-btn
      >
      <h2 class="counter-value">{{ value }}</h2>
      <q-btn v-touch-repeat.mouse="increment" class="btn right" flat
        ><p>+</p></q-btn
      >
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  width: 100% !important;
  height: 100% !important;
}
.btn {
  width: 100%;
  height: 100%;
  p {
    font-size: 2em;
    margin: 0 !important;
  }
}

.left {
  border-top: 2px solid black;
  border-left: 2px solid black;
  border-bottom: 2px solid black;
  border-radius: 4px 0px 0px 4px;
}

.right {
  border-top: 2px solid black;
  border-bottom: 2px solid black;
  border-right: 2px solid black;
  border-radius: 0px 4px 4px 0px;
}

.counter-value {
  position: absolute;
  margin: 0;
  // top: 50%;
  // left: 50%;
}
</style>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Counter',

  // props: {
  //   defaultValue: { type: Number, required: true },
  // },

  setup() {
    // TODO: setup an appropriate default value for the counter
    const value = ref(0);

    return {
      // Data
      value,
      // Methods
      increment: () => {
        value.value += 1;
      },
      decrement: () => {
        value.value -= 1;
      },
      longPressIncrement: () => {
        // console.log(evt);
        value.value += 10;
      },
      longPressDecrement: () => {
        // console.log(evt);
        value.value -= 10;
      }
    };
  }
});
</script>
