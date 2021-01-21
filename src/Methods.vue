<template>
<h5>Method examples</h5>
    <div> {{3 + 5 +1}} </div>
    <!-- <p>Calling add() method: {{ add() }} </p> -->
    <p>Calling with parameters: {{ add(7,14,2) }} </p>
    <p>Multiply by five: {{ multiply(7) }}</p>
</template>

<script>
    export default {
        name: 'Method',
        data() {
            return {
            baseMultiplier: 5
            }
        },
        methods: {
            add(a,b,c) {
                return a + b + c
            }, 
            multiply(num) {
                // use "this" keyword in the script
                return num * this.baseMultiplier
            },
        },
    }
</script>

<style scoped>
    h5 {
        background-color: yellow;
    }
</style>