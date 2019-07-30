<template>
  <div id="app">
   
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
*{
  padding:0;
  margin:0
}
html,body{
  width:100%;
  height:100%;

}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width:100%;
  height:100%;
  /* margin-top: 60px; */
}
.my-div-icon,
.my-div-area {
  width: 90px !important;
  height: 16px !important;
  background: rgba(3, 3, 3, 0.4);
  text-align: center;
  border-radius: 8px;
  color: #fff;
}
.my-div-area {
  width: 130px !important;
  display: none;
}
</style>
