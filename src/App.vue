<template>
  <el-table :data="filterTableData" style="width: 100%">
    <el-table-column label="Date" prop="date" />
    <el-table-column label="Name" prop="name" />
    <el-table-column>
      <template #header>
        <tr
          style="
            display: block;
            text-align: center;
            width: 100%;
            border: 1px solid #ccc;
          "
        >
          3333
        </tr>
        <tr
          style="
            display: block;
            text-align: center;
            width: 100%;
            border: 1px solid #ccc;
          "
        >
          3333
        </tr>
      </template>
      <template #default="scope">
        <tr
          style="
            display: block;
            text-align: center;
            width: 100%;
            border: 1px solid #ccc;
          "
        >
          data
        </tr>
        <tr
          style="
            display: block;
            text-align: center;
            width: 100%;
            border: 1px solid #ccc;
          "
        >
          data
        </tr>
      </template>
    </el-table-column>
  </el-table>
</template>

<script lang="ts" setup>
import { computed, ref } from 'vue'

interface User {
  date: string
  name: string
  address: string
}

const search = ref('')
const filterTableData = computed(() =>
  tableData.filter(
    data =>
      !search.value ||
      data.name.toLowerCase().includes(search.value.toLowerCase())
  )
)
const handleEdit = (index: number, row: User) => {
  console.log(index, row)
}
const handleDelete = (index: number, row: User) => {
  console.log(index, row)
}

const tableData: User[] = [
  {
    date: '2016-05-03',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles'
  },
  {
    date: '2016-05-02',
    name: 'John',
    address: 'No. 189, Grove St, Los Angeles'
  },
  {
    date: '2016-05-04',
    name: 'Morgan',
    address: 'No. 189, Grove St, Los Angeles'
  },
  {
    date: '2016-05-01',
    name: 'Jessy',
    address: 'No. 189, Grove St, Los Angeles'
  }
]
</script>
