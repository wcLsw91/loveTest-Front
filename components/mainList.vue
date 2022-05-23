<template>
  <div>
    <p v-if="$fetchState.pending">Loading....</p>
    <p v-else-if="$fetchState.error">Error while fetching mountains</p>
<!--    <ul v-else>-->
<!--      <li v-for="(mountain, index) in mountains" :key="index.id">-->
<!--        {{ mountain.title }}-->
<!--      </li>-->
<!--    </ul>-->
    <div v-else>{{ data }}</div>
  </div>
</template>

<script>
export default {
  name: "mainList",
  data() {
    return {
      data: []
    }
  },
  async fetch() {
    this.data = await fetch(
      'http://localhost:3000/api/question/1'
    ).then((res) => res.json())
  }
}
</script>

<style scoped>

</style>
