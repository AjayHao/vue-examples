<template>
  <div id="app2">
    <img src="./assets/logo.png">
    <h1>Hello App!</h1>
    <ul>
        <li><router-link to="/first">点我跳转到第一页</router-link></li>
        <li><router-link to="/second">点我跳转到第二页</router-link></li>
    </ul>
    <router-view class="view"></router-view>
  </div>
</template>

<script>
    export default {
        data() {
            return {
                aaa: '123'
            }
        }
    }

</script>

<style>
body {
  font-family: Helvetica, sans-serif;
}
</style>
