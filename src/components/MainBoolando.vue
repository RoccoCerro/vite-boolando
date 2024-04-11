<script>
import ProductBoolando from "./ProductBoolando.vue"
import DataProducts from "../assets/db.json"

export default {
    data() {
        return {
            clothes: DataProducts.products,
            // clothes: [
            //     {
            //         brand: "Levi's",
            //         image: "../assets/1.webp",
            //         imageHover: "../assets/1b.webp",
            //         priceDiscount: 14.99,
            //         oldPrice: 29.99,
            //         discount: "-50%",
            //         description: "RELAX FIT TEE UNISEX",
            //         sustainability: "Sostenibilità",
            //     },
            //     {
            //         brand: "Levi's",
            //         image: "../assets/2.webp",
            //         imageHover: "../assets/2b.webp",
            //         priceDiscount: 14.99,
            //         oldPrice: 29.99,
            //         discount: "-50%",
            //         description: "RELAX FIT TEE UNISEX",
            //         sustainability: "Sostenibilità",
            //     },
            //     {
            //         brand: "Levi's",
            //         image: "../assets/3.webp",
            //         imageHover: "../assets/3b.webp",
            //         priceDiscount: 14.99,
            //         oldPrice: 29.99,
            //         discount: "-50%",
            //         description: "RELAX FIT TEE UNISEX",
            //         sustainability: "Sostenibilità",
            //     },
            //     {
            //         brand: "Levi's",
            //         image: "../assets/4.webp",
            //         imageHover: "../assets/4b.webp",
            //         priceDiscount: 14.99,
            //         oldPrice: 29.99,
            //         discount: "-50%",
            //         description: "RELAX FIT TEE UNISEX",
            //         sustainability: "Sostenibilità",
            //     },
            //     {
            //         brand: "Levi's",
            //         image: "../assets/5.webp",
            //         imageHover: "../assets/5b.webp",
            //         priceDiscount: 14.99,
            //         oldPrice: 29.99,
            //         discount: "-50%",
            //         description: "RELAX FIT TEE UNISEX",
            //         sustainability: "Sostenibilità",
            //     },
            //     {
            //         brand: "Levi's",
            //         image: "../assets/6.webp",
            //         imageHover: "../assets/6b.webp",
            //         priceDiscount: 14.99,
            //         oldPrice: 29.99,
            //         discount: "-50%",
            //         description: "RELAX FIT TEE UNISEX",
            //         sustainability: "Sostenibilità",
            //     }
            // ]
        }
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`${img}`, import.meta.url).href
        }
    },
    components: {
        ProductBoolando
    }
}
</script>

<template>
    <div class="container">
        <div class="row">
            <ProductBoolando v-for="dress in clothes" :products="dress" />
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../style/partials/mixin' as *;
@use '../style/partials/utilities' as *;

.row {
    flex-wrap: wrap;
    margin: -5px;
    padding: 20px 0;
}
</style>