<script>
import BadgesBoolando from "./BadgesBoolando.vue"

export default {
    data() {
        return {
            priceDisc: null,
        }
    },
    props: ["product"],
    components: {
        BadgesBoolando
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/${img}`, import.meta.url).href
        },
        isFavorites() {
            this.product.isInFavorites = !this.product.isInFavorites
        },
        priceDiscount() {
            for (let i = 0; i < this.product.badges.length; i++) {
                let el = this.product.badges[i];
                if (el.type.includes("discount")) {
                    const discount = (el.value.slice(1, 3) * this.product.price / 100)
                    this.priceDisc = (this.product.price - discount).toFixed(2)
                }
            }
        }
    },
    mounted() {
        this.priceDiscount();
    }
}
</script>

<template>
    <div class="card">
        <div class="card-img">
            <img :src="getImagePath(product.frontImage)" alt="dress-img">
            <img class="img_hover" :src="getImagePath(product.backImage)" alt="">
        </div>
        <div class="card-footer">
            <div class="brand">{{ product.brand }}</div>
            <p class="description">{{ product.name }}</p>
            <span v-if="priceDisc !== null" class="price-discount">{{ priceDisc }}</span>
            <span v-bind:class="{'old-price': priceDisc !== null}">{{ product.price }} &euro;</span>
        </div>
        <div class="button-dinamic display-flex">
            <BadgesBoolando v-for="badge in product.badges" :text="badge.value" :type="badge.type" />
        </div>
        <div @click="isFavorites" class="button-heart">
            <i :class="product.isInFavorites === true ? 'color-red' : ''" class="fa fa-solid fa-heart"></i>
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
    bottom: 80px;
    left: 0px;
    gap: 5px;

    div {
        color: white;
        padding: 3px 10px;
    }
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