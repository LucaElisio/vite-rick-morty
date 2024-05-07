<script>
export default {
    props:{
        charObj: Object
    },
    data(){
        return{

        };
    },
}
</script>

<template>
    <div class="card mb-4" style="width: 18rem;">
        <img :src="charObj.image" class="card-img-top" :alt="charObj.name">
        <div class="card-body">
            <h5 class="card-title">{{charObj.name}}</h5>
            <p class="card-text">{{charObj.status}}<br>{{charObj.species}}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.card {
    border: none;

    .card-img-top{
        border-radius: 50%;
    }
}
</style>