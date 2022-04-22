<template>
  <div class="home">

    <h2>{{ appTitle }}</h2>

    <div>

      <h3>{{ counterData.title }}:</h3>

      <button @click="decrementCounter(1)" class="btn">-</button>
      <button @click="decrementCounter(2)" class="btn">--</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="incrementCounter(1, $event)" class="btn">+</button>
      <button @click="incrementCounter(2)" class="btn">++</button>
    </div>

    <p>This counter is {{ oddOrEven }}</p>

    <div class="edit">
      <h4>Edit counter title:</h4>
      <input v-model="counterData.title" type="text">
    </div>

  </div>
</template>

<script setup>
/*
* imports
*/

import {
  reactive,
  computed,
  watch,
  onBeforeUnmount,
  onBeforeMount,
  onMounted,
  onUnmounted,
  onActivated,
  onDeactivated, onBeforeUpdate, onUpdated
} from 'vue'

/*
* app title
*/

const appTitle = 'My Ok Counter App'

onMounted(() => {
  console.log('Do stuff related to App Title')
})

/*
* counter
*/

const counterData = reactive({
  count: 0,
  title: 'My Counter'
})

watch(() => counterData.count, (newCount) => {
  if (newCount === 20) {
    alert('Way to go! You made it to 20!!')
  }
})

const oddOrEven = computed(() => {
  if (counterData.count % 2 === 0) return 'even'
  return 'odd'
})

const incrementCounter = (amount, e) => {
  counterData.count += amount
  // console.log(e)
  console.log(counterData.count)
}

const decrementCounter = amount => {
  if (counterData.count > 0) {
    counterData.count -= amount
  }
  console.log(counterData.count)
}

onMounted(() => {
  console.log('Do stuff related to Counter')
})

// onBeforeUpdate(() => {
//   console.log('onBeforeUpdate')
// })
//
// onUpdated(() => {
//   console.log('onUpdated')
// })
//
// onBeforeMount(() => {
//   console.log('onbeforeMount')
// })
//
// onMounted(() => {
//   console.log('onMounted')
// })
//
// onBeforeUnmount(() => {
//   console.log('onBeforeUnmount')
// })
//
// onUnmounted(() => {
//   console.log('onUnmounted')
// })
//
// onActivated(() => {
//   console.log('onUnmounted')
// })
//
// onDeactivated(() => {
//   console.log('onUnmounted')
// })

</script>


<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      count: 0-->
<!--    }-->
<!--  },-->
<!--  computed: {-->
<!--    myComputedProperty() {-->
<!--      // perform logic based on a data property-->
<!--      return 'my result'-->
<!--    }-->
<!--  },-->
<!--  watch: {-->
<!--    count(newCount, oldCount) {-->
<!--      if (newCount == 20) alert('asdfasd')-->
<!--    }-->
<!--  },-->
<!--  mounted() {-->
<!--    // do stuff when component is loaded-->
<!--    console.log('mounted')-->
<!--  },-->
<!--  unmounted() {-->
<!--    // do stuff when component is loaded-->
<!--    console.log('unmounted')-->
<!--  }-->
<!--}-->
<!--</script>-->

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