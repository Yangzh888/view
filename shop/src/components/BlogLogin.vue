<template>
  <div>
    <blog-header></blog-header>
    <hr/>
    <div>
      用户名:<input type="text" v-model="user.username" placeholder="请输入用户名" />
      <br/>
      密码：<input type="password" v-model="user.password" placeholder="请输入密码" />
      <br/>
      <button v-on:click="login">登录</button>
      <br/>
      登录验证情况：<textarea cols="30" rows="10" v-model="responseResult"></textarea>
    </div>
    <hr/>
    <blog-footer></blog-footer>
  </div>
</template>

<script>
import blogHeader from '@/components/BlogHeader.vue'
import blogFooter from '@/components/BlogFooter.vue'

export default {
  name: 'BlogLogin',
  // blogHeader、blogFooter组件给申明到components里面然后在template里面使用
  components: { blogHeader, blogFooter },
  data () {
    return {
      user: { username: '', password: '' },
      responseResult: []
    }
  },
  methods: {
    login () {
      this.$axios
        .post('/login', {
          username: this.user.username,
          password: this.user.password
        })
        .then(successResponse => {
          this.responseResult = JSON.stringify(successResponse.data)
          alert(responseResult);
          if (successResponse.data.code === 200) {
            this.$router.replace({path: '/index'})
          }
        })
        .catch(failResponse => {})
    }
  }
}
</script>