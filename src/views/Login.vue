<template>
  <div class="container">
    <form action="" v-if="!isReg">
      <div><input type="text" v-model="name" placeholder="用户名："></div>
      <div><input type="password" v-model="password" placeholder="密码："></div>
      <div>
        <button type="button" @click="login()">登录</button>
        <button type="button" @click="reg()">注册</button>
      </div>
    </form>
    <form action="" v-else>
      <div><input type="text" v-model="name" placeholder="用户名："></div>
      <div><input type="password" v-model="password" placeholder="密码："></div>
      <div><input type="password" v-model="password" placeholder="确认密码："></div>
      <div>
        <button type="button" @click="addUser()">确定</button>
        <button type="button" @click="cancel()">取消</button>
      </div>
    </form>
  </div>
</template>

<script>
  export default {
    name: 'Login',
    data() {
      return {
        isReg: false,
        name: '',
        password: '',
        repeat: '',
      };
    },
    methods: {
      login() {
          if (localStorage.getItem('name') === this.name && localStorage.getItem('password') === this.password) {
              this.name = '';
              this.password = '';
              this.$router.push('/home/list');
          } else {
              alert('密码错误！');
              this.password = '';
          }
      },
      reg() {
        this.isReg = true;
      },
      cancel() {
        this.isReg = false;
      },
      addUser() {
        if (this.password === this.repeat) {
          localStorage.setItem('name', this.name);
          localStorage.setItem('password', this.password);
          this.name = '';
          this.password = '';
          this.isReg = false;
        } else {
          alert('两次密码不一致！');
        }
      },
    },
  };

</script>

<style scoped>
.container{
    text-align: center;
}
input{
  width: 200px;
  height: 30px;
  margin-top: 30px;
}

</style>
