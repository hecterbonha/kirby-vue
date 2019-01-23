<template>
  <div>
    <section class="balloon nes-container with-title">
      <h2 class="title">VueJS</h2>
      <div class="messages">
        <div class="nes-balloon from-right">
          <p>Hello this is vue componenet</p>
        </div>
      </div>
    </section>
    <Counter messageText="Let's Jump!!" />
    <List />
  </div>
</template>

<script>
import Counter from './components/Counter.vue';
import List from './components/List.vue';

export default {
  name: 'app',
  components: {
    Counter,
    List
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
