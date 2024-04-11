<script>

</script>

<template>
    <div class="container conclusion">
        <div class="row ">
            <div class="col doc">
                <h3>
                    Boolando s.r.l
                </h3>
                <ul>
                    <li>Informazioni legali</li>
                    <li>Informativa sulla privacy</li>
                    <li>Diritto di recesso</li>
                </ul>
            </div>
            <div class="col social">
                <h3>Trovaci anche su</h3>
                <ul class="row social">
                    <li>
                        <a href="#" class="fa fa-twitter"></a>
                    </li>
                    <li>
                        <a href="#" class="fa fa-facebook"></a>
                    </li>
                    <li>
                        <a href="#" class="fa fa-instagram"></a>
                    </li>
                    <li>
                        <a href="#" class="fa fa-pinterest"></a>
                    </li>
                    <li>
                        <a href="#" class="fa fa-youtube"></a>
                    </li>
                </ul>     
            </div>
        </div>
    </div>
</template>
 
<style lang="scss" scoped>
    @use '../style/partials/mixin' as *;

    .container.conclusion{
        height: 60px;

        .row{
            height: 100%;
            @include display-flex
        }

        ul{
            display: flex;
            gap: 7px;
        }
    }
</style>