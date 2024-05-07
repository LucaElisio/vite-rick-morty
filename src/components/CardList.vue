<script>
import AppChar from './AppChar.vue';
import { store } from "../store";



export default {
    components:{
        AppChar
    },

    data() {
    return {
        store
    };
    },
};
</script>

<template>
    <div class="container text-center">
        <div class="row">
            <div class="col" v-for="curChar in store.characterArray">
                <AppChar :charObj="curChar"/>
            </div>
        </div>
    </div>
</template>

<style scoped>
</style>