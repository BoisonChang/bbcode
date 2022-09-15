<template>
  <Message :html="bbcode" />
</template>

<script setup>
import { ref } from 'vue';
import Message from './components/MessageArea';

const bbcode = ref(
  'Hi #smile#, we are Code Zero #smile#shy#.\n' +
  'Happy `Coding` #heart#.\n' +
  '`#smile#` :)'
);
</script>

<style>

</style>
