<template>
  <HeaderVue/>
  <TextEditorVue />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import TextEditorVue from './components/TextEditor.vue';
import HeaderVue from './components/Header.vue'

export default defineComponent({
  name: 'App',
  components: {
    TextEditorVue,
    HeaderVue
  }
});
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    transition: 0.4s;
    font-family: Arial, Helvetica, sans-serif;
    box-sizing: border-box;
  }

  body {
    background-color: #111213;
    color: #f1f2f3;
  }
</style>
