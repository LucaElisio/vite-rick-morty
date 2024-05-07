<script>
import { store } from "../store";

export default {
    data() {
        return{
            store
        }
    },
}
</script>

<template>
    <div class="text-center mb-5">Mostrati {{this.store.characterArray.length}} risultati</div>
</template>

<style scoped>

</style>