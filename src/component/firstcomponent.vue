<template>
  <div id="FirstComponent">
    <h1>I am a component. Say '{{ words }}', passed in: {{ param }}</h1>
    <input v-model="message">
    <button v-on:click="reverse">Reverse Message</button>
  </div>
</template>

<script type="text/javascript">
module.exports = {

    data: function () {
        return {
            words: "Hello Vue!",
            message: "msg",
            param: '111'
        }
    },
    created: function () {
        console.log('FirstComponent created');
    },
    mounted: function () {
        console.log('FirstComponent mounted');
    },
    computed: {
        reverseMessage: function () {
            this.message = this.message.split('').reverse().join('')
        }
    },
    methods: {
        reverse: function() {
            this.reverseMessage();
        }
    }
}
</script>

<style>

</style>
