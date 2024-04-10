<script>

</script>

<template>
    <div class="container debug">
        <div class="row">
            <div class="col-4">
                <div class="card">
                    <div class="card-img">
                        <img src="../assets/1.webp" alt="">
                    </div>
                    <div class="card-footer">
                        <div class="brand">Levis's</div>
                        <p class="description">RELAX FIT TEE UNISEX</p>
                        <span class="price-discount">14,99 &euro;</span>
                        <span class="old-price">29,99 &euro;</span>
                    </div>
                    <div class="button-discount">-50%</div>
                    <div class="button-sustainability">Sostenibilità</div>
                    <div class="button-heart">&hearts;</div>
                </div>
            </div>
            <div class="col-4">
                <div class="card">
                    <div class="card-img">
                        <img src="../assets/1.webp" alt="">
                    </div>
                    <div class="card-footer">
                        <div>Levis's</div>
                        <p>RELAX FIT TEE UNISEX</p>
                        <span>14,99 &euro;</span>
                        <span>29,99 &euro;</span>
                    </div>
                </div>
            </div>
            <div class="col-4">
                <div class="card">
                    <div class="card-img">
                        <img src="../assets/1.webp" alt="">
                    </div>
                    <div class="card-footer">
                        <div>Levis's</div>
                        <p>RELAX FIT TEE UNISEX</p>
                        <span>14,99 &euro;</span>
                        <span>29,99 &euro;</span>
                    </div>
                </div>
            </div>
            <div class="col-4">
                <div class="card">
                    <div class="card-img">
                        <img src="../assets/1.webp" alt="">
                    </div>
                    <div class="card-footer">
                        <div>Levis's</div>
                        <p>RELAX FIT TEE UNISEX</p>
                        <span>14,99 &euro;</span>
                        <span>29,99 &euro;</span>
                    </div>
                </div>
            </div>
            <div class="col-4">
                <div class="card">
                    <div class="card-img">
                        <img src="../assets/1.webp" alt="">
                    </div>
                    <div class="card-footer">
                        <div>Levis's</div>
                        <p>RELAX FIT TEE UNISEX</p>
                        <span>14,99 &euro;</span>
                        <span>29,99 &euro;</span>
                    </div>
                </div>
            </div>
            <div class="col-4">
                <div class="card">
                    <div class="card-img">
                        <img src="../assets/1.webp" alt="">
                    </div>
                    <div class="card-footer">
                        <div class="">Levis's</div>
                        <p>RELAX FIT TEE UNISEX</p>
                        <span>14,99 &euro;</span>
                        <span>29,99 &euro;</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../style/partials/mixin' as *;
    @use '../style/partials/utilities' as *;

    .container{
        padding: 20px 0;
    }

    .card{
        @include card
    }

    .row{
        flex-wrap: wrap;
        margin: -5px;
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