<template>
  <div class="about">
    <h1 v-show="showHeader">{{ headerMessage }}</h1>
    <!-- <div>
      <button @click="increment">Click me</button>
      {{ counter }}
    </div> -->
    <!-- <div>
      <input type="text" v-model="myInputText" />

      {{  myInputText }}
    </div> -->
<!-- 
    <div>
      <div v-html="myHtml"></div>
    </div> -->
  </div>
</template>

<script>
export default {
  name: 'AboutView',
  data() {
    return {
      headerMessage: 'About Us',
      showHeader: true,
      counter: 0,
      myInputText: '',
      myHtml: '<h1>My html</h1>'
    }
  },
  computed: {
    reversedHeaderMessage() {
      return this.headerMessage.split('').reverse().join('')
    }
  },
  methods: {
    increment() {
      this.counter++
    }
  }
}
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>

