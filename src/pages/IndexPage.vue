<template>
  <q-page>
    <Counter />
  </q-page>
</template>

<script lang="ts">
import Counter from 'components/Counter.vue';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'IndexPage',
  components: { Counter }
});
</script>
