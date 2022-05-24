<template>
  <div class="startP_card">
    <h1>{{$route.params.title}}</h1>
    <h5>{{$route.params.description}}</h5>
    <img class="startP_img" src="../../assets/logo.svg"/>
    <button type="button" class="btn btn-outline-primary startP_btn">{{$route.params.button_text}}</button>
  </div>
</template>

<script>
export default {
  name: "start"
}
</script>

<style scoped>
.startP_card{
  width: var(--wrapper-width-min);
}
.startP_img{
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.startP_btn{
  margin-top: 50px;
}
</style>
