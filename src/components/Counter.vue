<template>
  <section class="ballon nes-container is-centered">
    <div class="hello">
      <h1>{{ messageText }}</h1>
      <p>
        Count Me
      </p>
      <p>{{counter}}</p>
      <div class="kirby-jump">
        <i class="nes-kirby" v-bind:class="{ jumpKirby: isJumping }"></i>
      </div>
      <br>
      <button class="nes-btn" v-bind:class="{ 'is-disabled': isDisabled }" v-on:click="jump()">Jump</button>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Counter',
  props: {
    messageText: String
  },
  data: function () {
    return {
      counter: 0,
      isJumping: false,
      isDisabled: false
    }
  },
  methods: {
    jump () {
      this.isDisabled = true;
      this.isJumping = true;
      setTimeout(function () {
        this.counter ++;
      }.bind(this), 500)
      setTimeout(function () {
          this.isJumping = false;
          this.isDisabled = false
      }.bind(this), 1000)
    },
    test () {
      console.log('Yuhu');
      this.isDisabled = true;
      this.isJumping = true;
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.kirby-jump {
  padding-top: 150px;
}
</style>
