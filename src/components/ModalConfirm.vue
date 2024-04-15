<script>
export default {
    props: {
        open: {
            type: Boolean,
            default: false
        },
        modelProduct: Object,
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/${img}`, import.meta.url).href
        }
    },
}
</script>

<template>
    <div v-if="open === true" class="modal-wrapper" @click="$emit('closeModal')">
        <div class="modal">
            <div class="container">
                <div class="row modal-row">
                    <div class="col-6 modal-image">
                        <div class="row">
                            <div class="col front-image">
                                <img :src="getImagePath(modelProduct.frontImage)" alt="frontImage">
                            </div>
                            <div class="col back-image">
                                <img :src="getImagePath(modelProduct.backImage)" alt="">
                            </div>
                        </div>
                    </div>
                    <ul class="col-6 modal-description">
                        <li>
                            Brand: {{ modelProduct.brand }}
                        </li>
                        <li>
                            Name: {{ modelProduct.name  }}
                        </li>
                        <li >
                            Prezzo: {{ modelProduct.price }}
                        </li>
                        <li v-if="modelProduct.isInFavorites === true" class="is-favorites">
                            Tra i tuoi preferiti!
                        </li>
                    </ul>
                    <button @click="$emit('closeModal')">Chiudi</button>
                </div>
            </div>
        </div>
    </div>
</template> 

<style lang="scss" scoped>

    .modal-wrapper{
        width: 100%;
        height: 100vh;
        position: fixed;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        background-color: rgba(0, 0, 0, 0.719);
        display: flex;
        align-items: center;
        justify-content: center;
        color: white;
        z-index: 1;
    }
        .modal{
            padding: 15px;
            border: 1px solid white;
            border-radius: 8px;
            position: relative;
        }

        button{
            position: absolute;
            bottom: 10px;
            right: 10px;
            color: rgb(99, 23, 18);
            padding: 5px 8px;
            border-radius: 12px;
            font-weight: bold;
            border: none;
            background-color: rgba(255, 255, 255, 0.273);
            font-size: 16px;
            cursor: pointer;

            &:hover{
                background-color: rgba(0, 0, 0, 0.185);
            }
        }

        .modal-row{
            gap: 50px;
        }

        .modal-image{
            padding: 10px;

            & .row{
                gap:5px
            }

            img{
                object-fit: cover;

            }

            .back-image{
                
                & img{
                    border-bottom-right-radius: 50px;

                }
            }
        }

        .modal-description{
            padding: 10px;
            
            .is-favorites{
                padding-top: 20px;
            }
        
    }
</style>