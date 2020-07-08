<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
*{
  list-style: none;
  text-decoration: none;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  border-radius: 5px;
}
button{
  outline: none;
  margin: 20px 20px;
  width: 85px;
  height: 25px;
  font-size: 15px;
  background-color: #fff;
  border: solid 1px orange;
}
button:hover{
  color: #fff;
  background-color: orange;
  box-shadow: 2px 0 5px 0 white;
}
</style>
