<script>
export default{
    data(){
        return{
            uomo: "Uomo",
            donna: "Donna",
            bambino: "Bambino",
            logo: '../assets/boolean-logo.png',
            user: '<i class="fa-solid fa-user"></i>',
            heart: '<i class="fa-regular fa-heart"></i>',
            bag: '<i class="fa-solid fa-bag-shopping"></i>'
        }
    }
}
</script>

<template>
    <div class="container">
        <div class="row">
            <div class="col">
                <span>{{ uomo }}</span>
                <span>{{ donna }}</span>
                <span>{{ bambino }}</span>
            </div>
            <div class="col">
                <img :src=logo alt="">
            </div>
            <div class="col">
                <span>{{ user }}</span>
                <span>{{ donna }}</span>
                <span>{{ bambino }}</span>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../style/partials/mixin' as *;

    .row{
        @include display-flex
    }
</style>