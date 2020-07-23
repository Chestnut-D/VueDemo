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
  border-radius: 3px;
}
#app{
  position: fixed;
  width: 100%;
  height: 100%;
  margin-left: -8px;
  margin-top: -8px;
  background-image: url(https://i.loli.net/2020/06/17/QJbavSTV1Hc4U8O.png);
  background-size: cover;
  color: white;
}
button{
  outline: none;
  margin: 20px 0;
  width: 105px;
  height: 25px;
  font-size: 15px;
  background-color: #fff;
  border: none;
}
button:hover{
  color: #fff;
  background-color: orange;
}
input,textarea{
    outline: none;
    border: 1px solid #fff;
}
input,textarea:focus{
    outline: none;
    box-shadow: 2px 0 2px 0 white;;
}
</style>
