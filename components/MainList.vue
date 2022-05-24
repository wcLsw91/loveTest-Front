<template>
  <div>
    <p v-if="$fetchState.pending">Loading....<lbar ref="loadingBar" :loading-f="true"/></p>
    <p v-else-if="$fetchState.error">Error while fetching mountains</p>
    <div v-else class="mainList">
      <div v-for="(test, index) in tests" :key="index.id" class="card" style="width: 18rem;" @click="moveToStartP(test)">
        <img class="card-img-top" src="../assets/logo.svg" alt="Card image cap">
        <div class="card-body">
          <h5 class="card-title">{{test.title}}</h5>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import lbar from "~/components/LoadingBar";

export default {
  name: "mainList",
  components:{lbar},
  data() {
    return {
      tests: [],
    }
  },
  async fetch() {
      this.tests = await fetch(
        'http://localhost:3000/api/tests'
      ).then((res) => res.json())
        .then(res => res.data)
  },
  methods:{
    moveToStartP(test){
      this.$router.push({name:'test-start',params:test})
    }
  }
}
</script>

<style scoped>
.card-body {
  flex: 1 1 auto;
  min-height: 1px;
  padding:1.25rem 0 0 0;
}
</style>
