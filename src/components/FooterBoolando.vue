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
                <ul>
                    <li>77</li>
                    <li>77</li>
                    <li>77</li>
                    <li>77</li>
                    <li>77</li>
                </ul>
            </div>
        </div>
    </div>
</template>
 
<style lang="scss" scoped>
    @use '../style/partials/mixin' as *;
    
    .row{
        @include display-flex
    }

    .container.conclusion{
        ul{
            display: flex;
            gap: 7px;
        }
    }
</style>