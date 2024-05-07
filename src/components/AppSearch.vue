<script>
import { store } from "../store";

export default {
    data() {
        return{
            store,
            selectedStatus: ["All", "Alive", "Dead", "Unknown"]
        }
    },
}
</script>

<template>
    <select class="form-select w-50 mx-auto mb-5" aria-label="Default select example" @change="$emit('statusChanged')" v-model="this.store.selectedStatus">
        <!-- <option selected>Open this select menu</option> -->
        <option :value="status" v-for="status in selectedStatus">{{status}}</option>

    </select>
</template>

<style scoped>

</style>