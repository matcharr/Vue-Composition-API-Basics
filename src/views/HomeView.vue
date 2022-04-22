<template>
  <div class="home">

    <div>
      <button @click="decrementCounter" class="btn">-</button>
      <span class="counter">{{ counter }}</span>
      <button @click="incrementCounter" class="btn">+</button>
    </div>

  </div>
</template>

<script setup>
  import { ref } from 'vue'

  const counter = ref(0)

  const incrementCounter = () => {
    counter.value++
  }

  const decrementCounter = () => {
    if (counter.value > 0) {
      counter.value--
    }
  }
</script>

<!--<script>-->
<!--import { ref } from 'vue'-->

<!--export default {-->
<!--  setup() {-->
<!--    const counter = ref(0)-->

<!--    const incrementCounter = () => {-->
<!--      counter.value++-->
<!--    }-->

<!--    const decrementCounter = () => {-->
<!--      counter.value&#45;&#45;-->
<!--    }-->

<!--    return {-->
<!--      counter,-->
<!--      incrementCounter,-->
<!--      decrementCounter,-->
<!--    }-->
<!--  }-->
<!--}-->
<!--</script>-->

<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      counter: 0-->
<!--    }-->
<!--  },-->
<!--  methods: {-->
<!--    incrementCounter() {-->
<!--      this.counter++-->
<!--    },-->
<!--    decrementCounter() {-->
<!--      this.counter&#45;&#45;-->
<!--    }-->
<!--  }-->
<!--}-->
<!--</script>-->

<style>
.home {
  text-align: center;
  padding: 20px;
}

.btn, .counter {
  font-size: 40px;
  margin: 10px;
}
</style>