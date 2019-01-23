<template>
  <section class="nes-container with-title is-centered">
    <h2 class="title">Kirby loves to eat</h2>
    <div class="lists">
        <template v-if="render">
          <ul class="nes-list is-disc">
            <li v-for="item in items" :key="item.id">
              {{ item.food }}
            </li>
          </ul>
        </template>
        <template v-if="!render">
          <button class="nes-btn is-primary" v-on:click="feedFoods()">Feed</button>
        </template>
    </div>
  </section>
</template>

<script>
import axios from 'axios'

export default {
  name: 'List',
  data: function () {
    return {
      render: false,
      items: null
    }
  },
  methods: {
    feedFoods () {
      this.render = true;
      axios({
        headers: {
          "Access-Control-Allow-Origin": "*",
          'Content-Type': 'application/json',
        },
        method:'get',
        responseType:'json',
        url:'http://localhost:1234/foods'
      })
      .then((response) => {
        this.items = response.data;
        console.log(items);
      });
    }
  }
}
</script>