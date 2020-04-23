<template>
    <div>
        <ul>
            <li>
                <label style="width: 145px">Название товара</label>
                <label style="width: 145px">Кол-во</label>
                <label style="width: 145px">Цена</label>
                <label style="width: 20%">Стоимость</label>
                <label style="width: 20%"></label>
            </li>
            <Product
                v-for="product in products"
                v-bind:product="product"
                v-on:remove-product="removeProduct"
            />
            <li>
                <span>
                    <label>Итоговая цена </label>
                    <label>{{ products.reduce((total, obj) => (obj.price * obj.count) + total,0) }}</label>
                </span>
            </li>
        </ul>
    </div>
</template>

<script>
    import Product from "@/components/Product";
    export default {
        props: ['products'],
        name: "Marketplace",
        components: {
            Product
        },
        methods: {
            removeProduct(id) {
                this.$emit('remove-product', id)
            }
        }
    }
</script>

<style scoped>
    ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }
    li {
        display: flex;
        border: 1px solid black;
        justify-content: space-between;
        max-width: 1000px;
        padding: .3rem;
        margin: 10px 0 10px 250px;
    }
</style>