<script>
export default {
    props: ["text", "type"],
}
</script>

<template>
    <!-- <div :class="text === 'Sostenibilità' ? 'background-green' : 'background-red'">
        {{ text }}
    </div> -->
    <div :class="`background-${type}`">
        {{ text }}
    </div>
</template>

<style scoped>
.background-discount {
    background-color: red;
    order: -1;
}

.background-tag {
    background-color: green;
}
</style>