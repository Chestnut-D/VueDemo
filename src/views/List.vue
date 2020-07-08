<template>
  <div id="content">
    <ul>
      <li v-for="(item,index) in pageLists" :key="index">
        <p>标题：{{item.title}}</p>
        <p>内容：{{item.content}}</p>
        <hr>
      </li>
    </ul>
  </div>
</template>

<script>
  import store from '@/store';

  export default {
    name: 'List',
    store,
    computed: {
      pageLists() {
        return store.state.lists;
      },
    },
  };

</script>

<style scoped>
li{
    margin-left: -30px;
}
</style>
