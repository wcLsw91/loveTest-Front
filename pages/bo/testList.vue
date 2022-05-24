<template>
  <div class="testList">
    <div class="table-top">
      <div/>
      <div class="btn-group">
        <button type="button" class="btn btn-light">삭제</button>
        <button type="button" class="btn btn-primary">등록</button>
      </div>
    </div>
    <table class="table">
      <thead class="thead-dark">
      <tr>
        <th scope="col">선택</th>
        <th scope="col">테스트 명</th>
        <th scope="col">등록일</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="(test,index) of tests" :key="index">
        <td><input type="checkbox"></td>
        <td>Otto</td>
        <td>@mdo</td>
      </tr>
      <tr>
        <th scope="row">2</th>
        <td>Jacob</td>
        <td>Thornton</td>
        <td>@fat</td>
      </tr>
      <tr>
        <th scope="row">3</th>
        <td>Larry</td>
        <td>the Bird</td>
        <td>@twitter</td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "testList",
  layout:'backOffice'
}
</script>

<style scoped>
.testList{
  width: 100%;
}
.table-top{
  display: flex;
  justify-content: space-between;
}
.testList .table-top .btn {
  margin-left: 10px;
}
</style>
