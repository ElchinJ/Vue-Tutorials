<template>
<main>

<h1>Fruit</h1>
    <ul>
        <li
            v-for="(item,index) in storeFruit"
            :key="index"
            @click="buy(item)"
        >{{item}}</li>
    </ul>
    <hr>
    <ul>
        <li v-for="(item,index) in basket"
            :key="index" 
            @click="removeItem(item, index)"        
        >{{item.count}}: {{item.fruit}}</li>
    </ul>
  </main>
</template>

<script>

export default {
    name: 'FruitSallad',
    data() {return {
        storeFruit: ["äpple","päron","melon","kiwi","apelsin"],
        basket: []
    }},
    methods: {
        move(item,index) {
            this.storeFruit.splice(index,1)
            this.basket.push(item)          
        },
        buy(item) {
            let find = this.basket.find(x => x.fruit == item)
            if(!find) {
                this.basket.push({count: 1, fruit: item}) 
            } else {
                find.count += 1
            }
        },
        removeItem(item, index) {
            this.basket.splice(index, 1)
        }
    }
    
}
</script>

<style>

</style>