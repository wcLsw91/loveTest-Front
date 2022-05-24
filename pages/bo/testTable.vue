<template>
  <div class="testList">
    <!--  table-top  -->
    <div class="table-top">
      <div/>
      <div class="btn-group">
        <button type="button" class="btn btn-light">삭제</button>
        <button type="button" class="btn btn-primary">등록</button>
      </div>
    </div>

    <!--  table  -->
    <DataTable
      :header-fields="headerFields"
      :data="data"
      :css="datatableCss"
      trackBy="title"
    />
  </div>
</template>

<script>
import { DataTable } from 'v-datatable-light'

export default {
  name: "testTable",
  layout:'backOffice',
  components: {
    DataTable
  },
  data(){
    return{
      data:[
        {title:'1111',createdAt:'11/22/33'},
        {title:'2222',createdAt:'11/22/33'},
        {title:'333',createdAt:'11/22/33'},
        {title:'444',createdAt:'11/22/33'},
        {title:'555',createdAt:'11/22/33'},
        {title:'6666',createdAt:'11/22/33'},
      ],
      headerFields:[
        "__slot:checkboxes",
        {name:'title',label:'테스트 명',sortable: false},
        {name:'createdAt',label:'등록일',sortable: false}
      ],
      datatableCss: {
        table: "table table-bordered table-hover table-striped table-center",
        th: "header-item",
        thWrapper: "th-wrapper",
        thWrapperCheckboxes: "th-wrapper checkboxes",
        arrowsWrapper: "arrows-wrapper",
        arrowUp: "arrow up",
        arrowDown: "arrow down",
        footer: "footer"
      },
    }
  }
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

/* Datatable CSS */
#v-datatable-light .header-item {
  cursor: pointer;
  color: #337ab7;
  transition: color 0.15s ease-in-out;
}

#v-datatable-light .header-item:hover {
  color: #ed9b19;
}

#v-datatable-light .header-item.no-sortable {
  cursor: default;
}
#v-datatable-light .header-item.no-sortable:hover {
  color: #337ab7;
}

#v-datatable-light .header-item .th-wrapper {
  display: flex;
  width: 100%;
  height: 100%;
  font-weight: bold;
}

#v-datatable-light .header-item .th-wrapper.checkboxes {
  justify-content: center;
}

#v-datatable-light .header-item .th-wrapper .arrows-wrapper {
  display: flex;
  flex-direction: column;
  margin-left: 10px;
  justify-content: space-between;
}

#v-datatable-light .header-item .th-wrapper .arrows-wrapper.centralized {
  justify-content: center;
}

#v-datatable-light .arrow {
  transition: color 0.15s ease-in-out;
  width: 0;
  height: 0;
  border-left: 8px solid transparent;
  border-right: 8px solid transparent;
}

#v-datatable-light .arrow.up {
  border-bottom: 8px solid #337ab7;
}

#v-datatable-light .arrow.up:hover {
  border-bottom: 8px solid #ed9b19;
}

#v-datatable-light .arrow.down {
  border-top: 8px solid #337ab7;
}

#v-datatable-light .arrow.down:hover {
  border-top: 8px solid #ed9b19;
}

#v-datatable-light .footer {
  display: flex;
  justify-content: space-between;
  width: 500px;
}
/* End Datatable CSS */
</style>
