<template>
<div>
    <div><input type="text" v-model="title" placeholder="标题"></div>
    <div class="tex"><textarea v-model="content" placeholder="内容"></textarea> </div>
    <button class="btn" @click="add()">添加</button>
</div>
</template>

<script>

import store from '@/store';

export default {
    name: 'Add',
    store,
    data() {
        return {
            title: '',
            content: '',
        };
    },
    methods: {
        add() {
            store.commit('addItem', {
                title: this.title,
                content: this.content,
            });
            this.title = '';
            this.content = '';
            this.$router.push('/home/list');
        },
    },
};

</script>

<style scoped>
input{
  width: 200px;
  height: 30px;
  margin-top: 30px;
}
.tex textarea{
    margin-top: 30px;
    width: 350px;
    height: 200px;
}

</style>
