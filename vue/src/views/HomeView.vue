<template>
  <div style="padding: 10px">
<!--    功能区域-->
    <div style="margin: 10px 0">
      <el-button type="primary">新增</el-button>
      <el-button type="primary">导入</el-button>
      <el-button type="primary">导出</el-button>
    </div>

<!--    搜索区域-->
    <div style="margin: 10px 0">
      <el-input v-model="search" placeholder="请输入关键字" style="width: 20%"/>
      <el-button type="primary" style="margin-left: 8px">查询</el-button>
    </div>
    <el-table :data="tableData" border stripe style="width: 100%">
      <el-table-column prop="date" label="日期" width="180" sortable/>
      <el-table-column prop="name" label="姓名" width="180" />
      <el-table-column prop="address" label="地址" width="" />
      <el-table-column fixed="right" label="操作" width="130">
        <template #default>
          <el-button size="small" @click="handleEdit"
          >编辑</el-button
          >
          <el-popconfirm title="你确定要删除吗?">
            <template #reference>
              <el-button type="danger" size="small">删除</el-button>
            </template>
          </el-popconfirm>

        </template>
      </el-table-column>
    </el-table>

    <div style="margin: 10px 0">
      <el-pagination
          v-model:currentPage="currentPage"
          v-model:page-size="pageSize"
          :page-sizes="[5, 10, 20]"
          :small="small"
          :disabled="disabled"
          :background="background"
          layout="total, sizes, prev, pager, next, jumper"
          :total="total"
          @size-change="handleSizeChange"
          @current-change="handleCurrentChange"
      />
    </div>
  </div>

</template>

<script>

export default {
  name: 'HomeView',
  components: {

  },
  data() {
    return {
      search: '',
      currentPage: 1,
      pageSize: 10,
      total: 10,
      tableData:[{
        date: '2021-09-11',
        name: 'Hovey',
        address: '杭州市钱塘区2号大街508号',
      },
        {
          date: '2022-05-02',
          name: 'Hovey',
          address: '杭州市钱塘区2号大街508号',
        },
        {
          date: '2022-02-04',
          name: 'Hovey',
          address: '杭州市钱塘区2号大街508号',
        },
        {
          date: '2022-05-01',
          name: 'Hovey',
          address: '杭州市钱塘区2号大街508号',
        },]
    }
  },
  methods: {
    handleEdit() {

    },
    handleSizeChange() {

    },
    handleCurrentChange() {

    }
  }

}

</script>
