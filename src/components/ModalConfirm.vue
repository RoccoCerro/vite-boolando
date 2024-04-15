<script>
export default {
    props: {
        open: {
        type: Boolean,
        default: false
        }
    }
}
</script>

<template>
    <div v-if="open === true" class="modal-wrapper">
        <div class="modal">
            <button @click="$emit('closeModal')">Chiudi</button>
            <p>Info Prodotto:</p>
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
        background-color: rgba(0, 0, 0, 0.226);
        display: flex;
        align-items: center;
        justify-content: center;
        color: white;
        z-index: 1;

        .modal{
            padding: 50px;
            border: 1px solid white;
            border-radius: 8px;

        }

        button{
            position: relative;
            bottom: 45px;
            right: 45px;
            color: rgba(99, 23, 18, 0.696);
            padding: 5px 8px;
            border-radius: 8px;
            font-weight: bold;
            border: none;
            background-color: rgba(255, 255, 255, 0.273);
            font-size: 10px;

            &:hover{
                background-color: rgba(0, 0, 0, 0.564);
            }
        }
    }
</style>