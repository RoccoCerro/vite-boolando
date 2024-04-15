<script>
import ProductBoolando from "./ProductBoolando.vue"
import DataProducts from "../assets/db.json"
import { store } from '../store.js'
import ModalConfirm from "./ModalConfirm.vue"

export default {
    data() {
        return {
            store,
            isOpen: false,
            indexOfModal: 0,
        }
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`${img}`, import.meta.url).href
        },
        viewModal(i){
            this.isOpen = true;
            this.indexOfModal = i
        }
    },
    components: {
        ProductBoolando,
        ModalConfirm
    },
    mounted(){
        console.log("array",this.store.clothes);
        // console.log(this.store.clothes[1].backImage);
    }
}
</script>

<template>
    <div class="container">
        <div class="row">
            <div class="col-4" v-for="(dress, i) in store.clothes">
                <ProductBoolando @showProduct="viewModal(i)" :product="dress" />
            </div>
            <ModalConfirm @closeModal="isOpen = false" :open="isOpen" :modelProduct="store.clothes[indexOfModal]"/> 
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