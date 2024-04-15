<script>
import ProductBoolando from "./ProductBoolando.vue"
import DataProducts from "../assets/db.json"
import { store } from '../store.js'
import ModalConfirm from "./ModalConfirm.vue"

export default {
    data() {
        return {
            stores: store,
            isOpen: false,
        }
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`${img}`, import.meta.url).href
        },
        viewModal(){
            this.isOpen = true
        }
    },
    components: {
        ProductBoolando,
        ModalConfirm
    }
}
</script>

<template>
    <div class="container">
        <div class="row">
            <div class="col-4" v-for="dress in stores.clothes">
                <ProductBoolando @showProduct="viewModal" :product="dress" />
                <ModalConfirm @closeModal="isOpen = false" :open="isOpen"/>
            </div>
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

.col-4 {
    padding: 10px 5px;
}
</style>