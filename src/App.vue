<template>
  <div class="table-box">
    <!--  标题-->
    <div class="title">
      <h2>简单CRUD的DEMO</h2>
    </div>
    <div class="query-box">
      <el-input v-model="queryInput" style="width: 240px" placeholder="请输入姓名"/>
      <el-button type="primary">增加</el-button>

    </div>

    <el-table :data="tableData" style="width: 100%">
      <el-table-column fixed prop="date" label="Date" width="150"/>
      <el-table-column prop="name" label="Name" width="120"/>
      <el-table-column prop="state" label="State" width="120"/>
      <el-table-column prop="city" label="City" width="120"/>
      <el-table-column prop="address" label="Address" width="600"/>
      <el-table-column prop="zip" label="Zip" width="120"/>
      <el-table-column fixed="right" label="Operations" min-width="120">
        <template #default>
          <el-button link type="primary" size="small" @click="handleRowClick">
            Detail
          </el-button>
          <el-button link type="primary" size="small">Edit</el-button>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script setup>

import {ref} from "vue";

let queryInput = ref();
let tableData = ref([
  {
    date: '2016-05-03',
    name: 'Tom',
    state: 'California',
    city: 'Los Angeles',
    address: 'No. 189, Grove St, Los Angeles',
    zip: 'CA 90036',
    tag: 'Home',
  },
  {
    date: '2016-05-02',
    name: 'Tom',
    state: 'California',
    city: 'Los Angeles',
    address: 'No. 189, Grove St, Los Angeles',
    zip: 'CA 90036',
    tag: 'Office',
  },
  {
    date: '2016-05-04',
    name: 'Tom',
    state: 'California',
    city: 'Los Angeles',
    address: 'No. 189, Grove St, Los Angeles',
    zip: 'CA 90036',
    tag: 'Home',
  },
  {
    date: '2016-05-01',
    name: 'Tom',
    state: 'California',
    city: 'Los Angeles',
    address: 'No. 189, Grove St, Los Angeles',
    zip: 'CA 90036',
    tag: 'Office',
  },

]);

const handleRowClick = () => {
  console.log("click");
}

</script>

<style scoped>

.table-box{
  width: 1000px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
}

</style>
