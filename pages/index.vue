<template>
<!--  <LazyMainList/>-->
  <div>
<!--    <p v-if="$fetchState.pending">Loading....</p>-->
<!--    <p v-else-if="$fetchState.error">Error while fetching mountains</p>-->
<!--    <ul class="mainList" v-else>-->
<!--      <li v-for="(mountain, index) in mainList" :key="index.id">-->
<!--        {{ mountain.title }}-->
<!--      </li>-->
<!--    </ul>-->

<!--    <div>{{data}}</div>-->

    <LazyMainList/>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      mainList: [],
      data:{},
    }
  },
  // async asyncData({ $axios, $config }) {
  //   const data = await $axios.$get(`/api/question/1`)
  //   return { data }
  // },
  // async fetch() {
  //   this.mainList = await fetch(
  //     'https://api.nuxtjs.dev/mountains'
  //   ).then((res) => res.json())
  // }
}
</script>
