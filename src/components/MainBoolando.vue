<script>
    export default{
        data(){
            return{
                clothes: [
                    {
                        brand: "Levi's",
                        image: "../assets/1.webp",
                        priceDiscount: 14.99,
                        oldPrice: 29.99,
                        discount: "-50%",
                        description: "RELAX FIT TEE UNISEX",
                        sustainability: "Sostenibilità",
                    },
                    {
                        brand: "Levi's",
                        image: "../assets/1.webp",
                        priceDiscount: 14.99,
                        oldPrice: 29.99,
                        discount: "-50%",
                        description: "RELAX FIT TEE UNISEX",
                        sustainability: "Sostenibilità",
                    },
                    {
                        brand: "Levi's",
                        image: "../assets/1.webp",
                        priceDiscount: 14.99,
                        oldPrice: 29.99,
                        discount: "-50%",
                        description: "RELAX FIT TEE UNISEX",
                        sustainability: "Sostenibilità",
                    },
                    {
                        brand: "Levi's",
                        image: "../assets/1.webp",
                        priceDiscount: 14.99,
                        oldPrice: 29.99,
                        discount: "-50%",
                        description: "RELAX FIT TEE UNISEX",
                        sustainability: "Sostenibilità",
                    },
                    {
                        brand: "Levi's",
                        image: "../assets/1.webp",
                        priceDiscount: 14.99,
                        oldPrice: 29.99,
                        discount: "-50%",
                        description: "RELAX FIT TEE UNISEX",
                        sustainability: "Sostenibilità",
                    },
                    {
                        brand: "Levi's",
                        image: "../assets/1.webp",
                        priceDiscount: 14.99,
                        oldPrice: 29.99,
                        discount: "-50%",
                        description: "RELAX FIT TEE UNISEX",
                        sustainability: "Sostenibilità",
                    }
                ]
            }
        },
        methods: {
            getImagePath: function(img) {
                return new URL(`${img}`, import.meta.url).href
            }
        }
    }
</script>

<template>
    <div class="container">
        <div class="row">
            <div v-for="dress in clothes" class="col-4">
                <div class="card">
                    <div class="card-img">
                        <img :src="getImagePath(dress.image)" alt="dress-img">
                    </div>
                    <div class="card-footer">
                        <div class="brand">{{ dress.brand }}</div>
                        <p class="description">{{ dress.description }}</p>
                        <span class="price-discount">{{ dress.priceDiscount }}</span>
                        <span class="old-price">{{ dress.oldPrice }} &euro;</span>
                    </div>
                    <div class="button-discount">{{ dress.discount }}</div>
                    <div class="button-sustainability">{{dress.sustainability}}</div>
                    <div class="button-heart">&hearts;</div>
                </div>
            </div>
        </div> 
    </div>
</template>

<style lang="scss" scoped>
    @use '../style/partials/mixin' as *;
    @use '../style/partials/utilities' as *;

    .card{
        @include card
    }

    .row{
        flex-wrap: wrap;
        margin: -5px;
        padding: 20px 0;
    }

    .col-4{
        position: relative;
        padding: 10px 5px;
    }

    .card-footer{
        .brand{
            font-size: $font-size-brand-and-price;
            color: rgba(0, 0, 0, 0.788);
        }
        .description,.price-discount{
            font-weight: bold;
        }
        .price-discount{
            color: $color-discount;
            padding-right: 5px;
        }
        .old-price{
            text-decoration: line-through;
        }
    } 

    .button-discount,.button-sustainability,.button-heart{
        position: absolute;
        text-align: center;
    }

    .button-discount,.button-sustainability{
        color: white;
        padding: 3px 10px;
    }
    
    .button-discount{
        background-color: $color-discount;
        bottom: 80px;
        left: 5px;
    }
    
    .button-sustainability{
        background-color: $color-button-sustainability;
        bottom: 80px;
        left: 65px;
    }

    .button-heart{
        background-color: white;
        width: 30px;
        font-size: 25px;
        aspect-ratio: 1/1;
        top: 5px;
        line-height: 30px;
        right: 0px;
    }
</style>