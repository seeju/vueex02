<template>
    <div>
        <h3>Novo produto</h3>
        <form @submit.prevent="onFormSubmit">
            <input type="text" placeholder="Nome" v-model="name"><br>
            <input type="number" min="1" step=".01" placeholder="Preço" v-model="price"><br>
            <input type="text" placeholder="Categoria" v-model="category"><br>
            <button type="submit">Adicionar</button><br>
        </form>
    </div>
</template>

<script>
    export default {
        name:"ProductForm",
        data () {
            return {
                name:"",
                price:"",
                category:"",
            }
        },

        props:{
            onAddProduct: Function,
        },

        methods: {
            onFormSubmit() {
                const product = {
                    name: this.name,
                    price: this.price,
                    category: this.category
                };
                this.onAddProduct(product);
            },
        },
    }
</script>

<style scoped>

input[type=number] {
  -moz-appearance: textfield;
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

</style>