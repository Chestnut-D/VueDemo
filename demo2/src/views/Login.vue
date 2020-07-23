<template>
  <div class="container">
    <form action="" v-if="!isReg">
      <h2>登录</h2>
      <div><input type="text" v-model="name" placeholder="用户名："></div>
      <div><input type="password" v-model="password" placeholder="密码："></div>
      <div class="log">
        <button type="button" @click="login()">登录</button>
        <button type="button" @click="reg()">注册</button>
      </div>
    </form>
    <form action="" v-else>
      <h2>注册</h2>
      <div><input type="text" v-model="name" placeholder="用户名："></div>
      <div><input type="password" v-model="password" placeholder="密码："></div>
      <div><input type="password" v-model="repeat" placeholder="确认密码："></div>
      <div class="log">
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
        if (this.password === '') {
          alert('请输入账号密码');
        } else if (localStorage.getItem('name') === this.name && localStorage.getItem('password') === this.password) {
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
  .container {
    margin-top: 200px;
    text-align: center;
    color: white;
  }

  input {
    width: 300px;
    height: 30px;
    margin-top: 20px;
  }

  .log button {
    margin: 30px 20px;
  }

</style>
