<template>
    <form @submit.prevent="onSubmit">
        <label>Название: </label>
        <input type="text" v-model="title">
        <label>Кол-во: </label>
        <input type="text" v-model="count">
        <label>Цена: </label>
        <input type="text" v-model="price">
        <button type="submit">Добавить</button>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                title: '',
                count: '',
                price: ''
            }
        },
        name: "AddProduct",
        methods: {
            onSubmit() {
                if(this.title.trim() && this.count.trim() && this.price.trim()){
                    const newProduct = {
                        id: Date.now(),
                        title: this.title,
                        count: this.count,
                        price: this.price
                    }
                    this.$emit('add-product', newProduct)
                }
            }
        }
    }
</script>

<style scoped>

</style>