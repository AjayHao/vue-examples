<template>
  <div id="firstcomponent">
    <h1>I am a component.</h1>
    <a> written by {{ author }} </a>
    <input v-model="message">
  </div>
</template>

<script type="text/javascript">
export default {

  data () {
    return {
      author: "Jinkey",
      message: "msg"
    }
  }
}
</script>

<style>

</style>
