<script>
export default {
    data() {
        return {
            links: [
                {
                    text: 'Uomo',
                    href: '#'
                },
                {
                    text: 'Donna',
                    href: '#'
                },
                {
                    text: 'Bambini',
                    href: '#'
                },
            ],
            logo: '../assets/boolean-logo.png',
            user: '<i class="fa fa-solid fa-user"></i>',
            heart: '<i class="fa fa-heart"></i>',
            bag: '<i class="fa-solid fa-bag-shopping"></i>',
        }
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`${img}`, import.meta.url).href
        }
    }
}
</script>

<template>
    <div class="container sidebar">
        <div class="row">
            <ul class="col clothes display-flex">
                <li v-for="link in links">{{ link.text }}</li>
            </ul>
            <div class="col logo">
                <img :src="getImagePath(logo)" alt="">
            </div>
            <div class="col connections">
                <span v-html="user"></span>
                <span v-html="heart"></span>
                <span v-html="bag"></span>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../style/partials/mixin' as *;

.container.sidebar {
    height: 60px;

    span:not(:last-of-type),
    li {
        padding-right: 10px;
    }
}

.row {
    @include display-flex;
    height: 100%;
}

.col.logo {

    img {
        max-width: 100px;
    }
}
</style>