<template>
  <div class="post-detail">
    <h1>This is a post page</h1>
    <p>Display the content of post with ID of {{ $route.params.id}} here!</p>

    <div>
      <button @click="showPostId"> Show Post ID</button>
    </div>

    <div>
      <boutton @click="goHomeIn3Seconds">Go Home in 3 seconds</boutton>
    </div>

    <div>
      <boutton @click="goToFirstPost">Go To First post</boutton>
    </div>

    <p><RouterLink to="/posts">&lt; Back</RouterLink></p>
  </div>
</template>

<script setup>
/*
* imports
*/
import { useRoute, useRouter } from 'vue-router'
const route =  useRoute()
const router =  useRouter()
const showPostId = () => {
  console.log('showPostId')
  alert(`The ID of this post is: ${ route.params.id }`)
}

const goHomeIn3Seconds = () => {
  setTimeout(() => {
   router.push({ name: 'home' })
  }, 3000)
}

const goToFirstPost = () => {
    router.push({
      name: 'postDetail',
      params: {
        id: 'id1'
      }
    })
}
</script>
