<template>
  <div>
    <div>
      <ul>
        <li>
          <router-link :to="{name: 'add'}">添加</router-link>
        </li>
        <li>
          <router-link :to="{name: 'add'}">添加</router-link>
        </li>
        <li>
          <router-link :to="{name: 'add'}">添加</router-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'User',
  };

</script>

<style scoped>
a{
    color: white;
}
</style>
