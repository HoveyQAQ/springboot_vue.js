<template>
  <!--  定义项目的头部、侧边栏、主体  -->
  <!--  头部通过组件的方式写  -->
  <div>
<!--  头部  -->
    <Header />
<!--  主体  -->
    <div style="display: flex">
<!--  侧边栏  -->
      <Aside />
<!--  内容区域  -->
      <router-view style="flex: 1"/>
    </div>
  </div>

</template>

<style>

</style>

<!--引进header-->
<script>
import Header from "@/components/Header";
import Aside from "@/components/Aside";
export default {
  name: "Layout",
  components: {
    /*选中组件 alt + enter 快捷键 导入*/
    Header,
    Aside
  }
}

</script>
<style scoped>
@import url("//unpkg.com/element-ui@2.15.6/lib/theme-chalk/index.css");
</style>