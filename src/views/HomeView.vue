<template>
  <div class="home">

    <h2>{{ appTitle }}</h2>

    <div>

      <h3>{{ counterData.title }}:</h3>

      <button @click="decrementCounter" class="btn">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="incrementCounter" class="btn">+</button>
    </div>

    <div class="edit">
      <h4>Edit counter title:</h4>
      <input v-model="counterData.title" type="text">
    </div>

  </div>
</template>

<script setup>
  import { reactive } from 'vue'

  const appTitle = 'My Counter App'

  // const counter = ref(0),
  //     counterTitle = ref('My Counter')

  const counterData = reactive({
    count: 0,
    title: 'My Counter'
  })

  const incrementCounter = () => {
    counterData.count++
  }

  const decrementCounter = () => {
    if (counterData.count > 0) {
      counterData.count--
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

.edit {
  margin-top: 60px;
}
</style>