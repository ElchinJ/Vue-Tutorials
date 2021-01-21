<template>
        <label>Change name with button click and back with mouse hover</label>
        <p @mouseover="initialName">{{ name }}</p>
        <button @click="changeName">Change name</button>
        <hr>

        <label>Increment and decrement with buttons</label>
        <p>Value: {{count}}</p>
        <button @click="increment">Increment</button>
        <button @click="decrement">Decrement</button>
        <button @click="multiplyBy">Multiply by: </button>
        <input type="number" placeholder="give a number">
        <hr>

        <label>Double event on click</label>
        <button @click="changeName(), increment()">Change name and value</button>
</template>

<script>
    export default {
        name: 'EventHandler',
        data() {
            return {
                name: 'Chino', 
                count: 0,
            }
        }, 
        methods: {
            changeName() {
                return this.name = 'Terminator'
            },
            initialName() {
                return this.name = 'Chino'
            }, 
            increment() {
                return this.count += 1
            }, 
            decrement() {
                return this.count -= 1
            }, 
            multiplyBy() {
                const value = document.querySelector('input').value
                return this.count *= value
            }
        }
    }
</script>

<style scoped>
    label {
        background-color: yellow;
    }
    button {
        margin-left: 1rem;
    }
    input {
        margin-left: 0.2rem;
        width: 6rem;
    }
</style>