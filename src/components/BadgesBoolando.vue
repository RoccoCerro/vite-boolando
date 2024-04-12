<script>
export default {
    props: ["text"],
}
</script>

<template>
    <div :class="text === 'Sostenibilità' ? 'background-green' : 'background-red'">
        {{ text }}
    </div>
</template>

<style></style>