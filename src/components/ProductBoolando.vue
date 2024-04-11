<script>
export default {
    props: ["products"],
    methods: {
        getImagePath: function (img) {
            return new URL(`${img}`, import.meta.url).href
        }
    }
}
</script>

<template>
    <div class="col-4">
        <div class="card">
            <div class="card-img">
                <img :src="getImagePath(products.image)" alt="dress-img">
                <img class="img_hover" :src="getImagePath(products.imageHover)" alt="">
            </div>
            <div class="card-footer">
                <div class="brand">{{ products.brand }}</div>
                <p class="description">{{ products.description }}</p>
                <span class="price-discount">{{ products.priceDiscount }}</span>
                <span class="old-price">{{ products.oldPrice }} &euro;</span>
            </div>
            <div class="button-discount">{{ products.discount }}</div>
            <div class="button-sustainability">{{ products.sustainability }}</div>
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