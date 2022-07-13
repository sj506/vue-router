<template>
  <div>
    <h1>Rendering</h1>
    <input type="text" v-model="type" />
    <h1 v-if="type === 'A'">A</h1>
    <h1 v-else-if="type === 'B'">B</h1>
    <h1 v-else>C</h1>
    <hr />
    <h1 v-show="type === 'A'">A</h1>
    <h1 v-show="type === 'B'">B</h1>
    <h1 v-show="type === 'C'">C</h1>
  </div>
</template>
<script>
export default {
  name: '',
  components: {},
  data() {
    return {
      type: 'A',
    };
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {},
};
</script>
