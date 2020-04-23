<template>
    <li>
        <input width="20%" type="text" autocomplete="False" v-model="product.title">
        <input width="20%" type="text" autocomplete="False" v-model="product.count">
        <input width="20%" type="text" autocomplete="False" v-model="product.price">
        <label style="width: 20%">{{product.price * product.count}}</label>
        <button style="width: 20%" v-on:click="$emit('remove-product', product.id)">&times;</button>
    </li>
</template>

<script>
    export default {
        props: {
            product: {
                type: Object,
                require: true
            }
        },
        name: "Product"
    }
</script>

<style scoped>

</style>