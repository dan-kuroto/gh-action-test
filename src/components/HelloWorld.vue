<script lang="ts">
export default {
  data: () => ({
    count: parseInt(localStorage.getItem('count') || '0'),
  }),
  methods: {
    increase() {
      this.count++;
      localStorage.setItem('count', this.count.toString());
    },
    reset() {
      this.count = 0;
      localStorage.removeItem('count');
    },
  },
  props: {
    msg: {
      type: String,
      required: true
    }
  },
}
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="increase">count is {{ count }}</button>
    <button type="button" @click="reset">clear</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
