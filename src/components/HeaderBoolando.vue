<script>

</script>

<template>
    <div class="container debug">
        <div class="row">
            <div class="col">
                donna
            </div>
            <div class="col">
                logo
            </div>
            <div class="col">
                tag
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../style/partials/mixin' as *;

    .debug.container{
        background-color: green;
    }

    .row{
        @include display-flex
    }
</style>