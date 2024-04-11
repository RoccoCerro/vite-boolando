<script>
export default {
    props: ["products"],
    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/${img}`, import.meta.url).href
        }
    }
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
                <span class="price-discount">{{ 50 * (products.price / 100) }}</span>
                <span class="old-price">{{ products.price }} &euro;</span>
            </div>
            <div v-if="products.badges[products.badges.length - 1].type === 'discount'" class="button-discount">
                {{ products.badges[products.badges.length - 1].value }}
            </div>
            <div v-if="products.badges[0].type === 'tag'" class="button-sustainability">
                {{ products.badges[0].value }}
            </div>
            <div class="button-heart">&hearts;</div>
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

.button-discount,
.button-sustainability,
.button-heart {
    position: absolute;
    text-align: center;
}

.button-discount,
.button-sustainability {
    color: white;
    padding: 3px 10px;
}

.button-discount {
    background-color: $color-discount;
    bottom: 80px;
    left: 5px;
}

.button-sustainability {
    background-color: $color-button-sustainability;
    bottom: 80px;
    left: 65px;
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