<template>
  <div id="app">
    <h1 class="title">Perguntas de conhecimentos gerais</h1>

    <FlashcardDeck />
  </div>
</template>

<script>
import FlashcardDeck from './components/FlaschardDeck.vue';

export default {
  name: 'App',
  components: {
    FlashcardDeck
  }
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 40px;
}

.title {
  font-size: 32px;
  font-weight: bold;
  margin-bottom: 40px;
  color: #2c3e50;
  font-family: Helvetica, Arial, sans-serif; /* Add the font-family property for Helvetica */
}
body {
  font-family: Helvetica, Arial, sans-serif;
  background-color: rgb(89, 122, 141);
}
</style>
