<template>
    <div>
        <h1>{{ msg }}</h1>
        <p>Quantidade: {{ productsCount }}</p>
        <table>
            <tr>
                <th>#</th>
                <th>Produto</th>
                <th>Quantidade</th>
                <th>Total</th>
            </tr>
            <tbody>
                <tr v-for="product in products" :key="product.id">
                    <td>{{ product.id }}</td>
                    <td>{{ product.name }}</td>
                    <td class="center">
                        <button @click="product.quant--">-</button>
                        <input class="cell-center" min="0" type="number" v-model="product.quant"/>
                        <button @click="product.quant++">+</button>
                    </td>
                    <td>{{total(product)}}</td>
                </tr>
            </tbody>
        </table>
        <p>Total: {{ productsTotal }}</p>     


    </div>
</template>

<script>

export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Shopping',
    props:{
        msg: String
    },
    data(){
        return{
            products:[
                {id: 1, name: "Sapato", quant: 5, price: 189.98 },
                {id: 2, name: "Bolsa", quant: 5, price: 120.97 },
                {id: 3, name: "Camiseta", quant: 5, price: 150.00},
                {id: 4, name: "Bermuda", quant: 5, price: 70.00 },
                {id: 5, name: "Meia", quant: 5, price: 50.00 },
            ]
        }
    },
    methods: {
        total(product){
            return (product.price * product.quant).toFixed(2)
        }
    },
    computed: {
        productsCount(){
            return this.products
            .map(product => product.quant)
            .reduce((pv,cv)=> pv += cv) 

        },
        productsTotal(){
            return this.products
            .map(product => product.quant * product.price)
            .reduce((pv,cv) => pv += cv)
            .toFixed(2)
        }
        
    },
}
</script>

<style scoped>
    .center{
        text-align: center;
    }
    .cell-center{
        max-width: 30px;
        display: inline-block;
    }
    h3 {
        margin: 40px 0 0;
    }
    th, td{
        border-top: 1px solid lightgray;
        padding: 5px 10px;
    }
    a{
        color: chocolate;
    }
</style>
