<script>
import BadgesBoolando from "./BadgesBoolando.vue"

export default {
    priceDisc: null,
    props: ["products"],
    components: {
        BadgesBoolando
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/${img}`, import.meta.url).href
        },
        isFavorites() {
            this.products.isInFavorites = !this.products.isInFavorites
        },
        // priceDiscount() {
        //     for (let i = 0; i < products.badges.length; i++) {
        //         let el = products.badges[i];
        //         if (el.includes("discount")) {
        //             this.priceDisc = products.badges[i] * products.price / 100
        //         }
        //     }
        // }
        // priceDiscount() {
        //     for (let i = 0; i < this.products.badges.length; i++) {
        //         let el = this.products.badges[i];
        //         if (el.type.includes("discount")) {
        //             this.priceDisc = this.products.badges[i] * this.products.price / 100
        //         }

        //         return priceDisc
        //     }
        // }
    },
    // computed: {
    //     priceDiscount() {
    //         for (let i = 0; i < this.products.badges.length; i++) {
    //             let el = this.products.badges[i];
    //             if (el.type.includes("discount")) {
    //                 this.priceDisc = this.products.badges[i] * this.products.price / 100
    //             }

    //             return priceDisc
    //         }
    //     }
    // }
    // mounted() {
    //     priceDiscount() {
    //         for (let i = 0; i < products.badges.length; i++) {
    //             let el = products.badges[i];
    //             if (el.type.includes("discount")) {
    //                 this.priceDisc = products.badges[i] * products.price / 100
    //             }
    //         }
    //     }
    // }
    // created() {
    //     this.priceDiscount()
    // }
}
</script>

<template>
    <div class="col-4">
        <div class="card">
            <div class="card-img">
                <img :src="getImagePath(products.frontImage)" alt="dress-img">
                <img class="img_hover" :src="getImagePath(products.backImage)" alt="">
            </div>
            <div class="card-footer">
                <div class="brand">{{ products.brand }}</div>
                <p class="description">{{ products.name }}</p>
                <!-- <span class="price-discount">{{ priceDisc }}</span> -->
                <span class="old-price">{{ products.price }} &euro;</span>
            </div>
            <div class="button-dinamic display-flex">
                <BadgesBoolando v-for="badge in products.badges" :text="badge.value" />
            </div>
            <div @click="isFavorites" class="button-heart">
                <i :class="products.isInFavorites === true ? 'color-red' : ''" class="fa fa-solid fa-heart"></i>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
@use '../style/partials/mixin' as *;
@use '../style/partials/utilities' as *;

.card {
    @include card;
    position: relative;
}

.col-4 {
    padding: 10px 5px;
}

.card-footer {
    .brand {
        font-size: $font-size-brand-and-price;
        color: rgba(0, 0, 0, 0.788);
    }

    .description,
    .price-discount {
        font-weight: bold;
    }

    .price-discount {
        color: $color-discount;
        padding-right: 5px;
    }

    .old-price {
        text-decoration: line-through;
    }
}

.button-dinamic,
.button-heart {
    position: absolute;
    text-align: center;
}

.button-dinamic {

    div {
        color: white;
        padding: 3px 10px;
    }
}

.button-dinamic {
    bottom: 80px;
    left: 0px;
    gap: 5px;
}

.button-heart {
    background-color: white;
    width: 30px;
    font-size: 25px;
    aspect-ratio: 1/1;
    top: 5px;
    line-height: 30px;
    right: 0px;
}

.img_hover {
    opacity: 0;
    position: absolute;
    left: 0px;
    top: 0px;

    &.img_hover:hover {
        opacity: 1;
    }
}
</style>