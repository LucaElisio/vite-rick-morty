<script>
import AppChar from './AppChar.vue';


export default {
    components:{
        AppChar
    },

    props:{
        characterArray: Array
    },

    data() {
    return {

    };
    },
};
</script>

<template>
    <div class="container text-center">
        <div class="row">
            <div class="col" v-for="curChar in characterArray">
                <AppChar :charObj="curChar"/>
            </div>
        </div>
    </div>
</template>

<style scoped>
</style>