<template>
    <div id="app">

        <Home></Home>
    </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Home from '@/Home.vue';
@Component({
    components: {
        Home
    }
})
export default class App extends Vue {} // 继承一个Vue的类
</script>
<style lang="stylus">
body
    margin 0
    padding 0

#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
}
</style>
