<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div>
    <Vueform>
      <!--label attribute is vulnerable to XSS.-->
      <TextElement name="hello_world" label="<img src=x onerror=alert(1) />" />
    </Vueform>
  </div>
  <HelloWorld msg="Vite + Vue"/>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
