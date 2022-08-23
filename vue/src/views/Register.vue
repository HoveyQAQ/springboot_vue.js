<template>
  <div style="width: 100%; height: 100vh; background-color: darkslateblue; overflow: hidden">
    <div style="width: 400px; margin: 100px auto">
      <div style="color: #cccccc; font-size: 30px; text-align: center; padding: 30px 0">欢迎登录</div>
      <el-form :model="form" size="normal">
        <el-form-item>
          <el-input :prefix-icon="User" v-model="form.username" />

        </el-form-item>
        <el-form-item>
          <el-input :prefix-icon="Lock" v-model="form.password" show-password/>
        </el-form-item>
        <el-form-item>
          <el-button style="width: 100%" type="primary" @click="login">登 录</el-button>
        </el-form-item>
      </el-form>
    </div>

  </div>
</template>

<script>
import { ArrowDown } from '@element-plus/icons-vue'
import request from "@/utils/request";
export default {
  name: "Login",
  components:{

    ArrowDown

  },
  data() {
    return {
      form: {}
    }
  },
  methods: {
    login() {
      request.post("/user/login", this.form).then(res => {
        if (res.code === '0') {
          this.$message({
            type: "success",
            message: "登录成功"
          })
          this.$router.push("/") // 登录成功 页面跳转
        } else {
          this.$message({
            type: "error",
            message: res.msg
          })
        }
      })
    }
  }

}
</script>
<script setup>
import { User, Lock} from '@element-plus/icons-vue'
</script>
<style scoped>

</style>