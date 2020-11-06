<template>
    <SpeakText />
</template>

<script>
import SpeakText from './components/SpeakText.vue';

export default {
    name: 'App',
    components: {
        SpeakText,
    },
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
