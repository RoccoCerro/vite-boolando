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
    <div class="container sidebar">
        <div class="row">
            <div class="col clothes">
                <span>{{ uomo }}</span>
                <span>{{ donna }}</span>
                <span>{{ bambino }}</span>
            </div>
            <div class="col logo">
                <img :src=logo alt="">
            </div>
            <div class="col connections">
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
        @include display-flex;
        height: 100%;
    }

    .container.sidebar{
        height: 100%;

        span:not(:last-of-type){
            padding-right: 10px;
        }
    }
</style>