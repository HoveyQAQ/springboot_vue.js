<template>
  <div>
    <el-menu
        style="width:200px; min-height: calc(100vh - 50px)"
        default-active="2"
        class="el-menu-vertical-demo">
        <el-sub-menu index="1">
          <template #title>
            <el-icon><location /></el-icon>
            <span>导航一</span>
          </template>
          <el-sub-menu index="1-1">
            <template #title>选项1</template>
            <el-menu-item index="1-1-1">选项1-1</el-menu-item>
          </el-sub-menu>


        </el-sub-menu>
        <el-menu-item index="2">
          <el-icon><icon-menu /></el-icon>
          <span>导航二</span>
        </el-menu-item>
        <el-menu-item index="3" disabled>
          <el-icon><document /></el-icon>
          <span>导航三</span>
        </el-menu-item>
        <el-menu-item index="4">
          <el-icon><setting /></el-icon>
          <span>导航四</span>
        </el-menu-item>
      </el-menu>
  </div>
</template>

<script>
import {
  Document,
  Menu as IconMenu,
  Location,
  Setting,
} from '@element-plus/icons-vue'
export default {
  name: "Aside",
  components:{

    Document,
    IconMenu,
    Location,
    Setting

  }
}
</script>

<style scoped>

</style>