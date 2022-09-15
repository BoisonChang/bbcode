<template>
<div>
    <h2 for="phone">BBCode</h2><br>
    <textarea v-model="input" @input="changeHandler"></textarea>
    <h2>HTML</h2><br>
    <p type="text" v-html="output"></p>｀
</div>
</template>


<script setup>
  /* eslint-disable */
  import { defineProps, ref } from "vue"
  defineProps({
    html: String,
  });
  let input = ref(), output = ref()
  const changeHandler = e => {
    const bold = /\[b\]([^\[\/b\]]+)\[\/b\]/g, code = /`([^`]+)`/g
    const smile =/\#smile\#/g, smileshy =/\#smile\#shy\#/g, heart =/\#heart\#/g
    output.value = e.target.value
    .replace(code, `<pre>$1</pre>`)
    .replace(bold, `<strong>$1</strong>`)
    .replace(smileshy, `<span>&#128522</span>`)
    .replace(smile, `<span>&#128512</span>`)
    .replace(heart, `<span>🧡</span>`)
  }
</script>