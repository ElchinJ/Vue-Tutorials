<template>
        <h5>List of array</h5>
        <p v-for='(name, index) in names' :key="name">{{index}} {{name}}</p>

        <h5>List of objects</h5>
        <p v-for="(name, index) in fullNames" :key="index">{{index}} {{name.firstName}} {{name.lastName}}</p>

        <h5>List of arrays in arrays</h5>
        <div v-for="actor in actors" :key="actor.name">{{actor.name}}
        <p v-for="movie in actor.movies" :key="movie">{{movie}}</p>
        </div>

        <h5>Object list</h5>
        <p v-for="value in kvn" :key="value">
            {{ value }}
        </p>
        <p v-for="(value, key, index) in kvn" :key="value">Another example: {{index}} {{key}} {{value}}</p>

        <h5>Key attributes</h5>
        <template v-for="player in players" :key="player">
            <p>{{player}}</p>
            <input placeholder="last name"/>
            <hr/>
        </template>
        <button @click="shuffle">Shuffle</button>

        <h5>Conditional List Rendering</h5>
        <template v-for="player in players" :key="player">
            <p v-if="player === 'Michael'">{{player}}</p>
        </template>
</template>

<script>
import _ from "lodash";
    export default {
        name: 'ListRendering',
        data() {
            return {
                names: ['Bruce', 'Clark', 'Milena', 'Diana'],
                fullNames: [
                    {firstName: 'Bruce', lastName: 'Lee'},
                    {firstName: 'Hanzo', lastName: 'Hasashi'},
                    {firstName: 'Bi', lastName: 'Han'},
                ],
                actors: [
                    {name: 'Christian Bale', movies: ['Batman', 'The Prestige']},
                    {name: 'Di Caprio', movies: ['Titanic', 'Inception']},
                ],
                kvn: {
                    team: 'Soyuz',
                    captain: 'Aydar Garayev',
                    title: '2015',
                }, 
                players:
                    ['Michael', 'ONeil', 'Bryant', 'Miller'],
            }
        },
        methods: {
            shuffle() {
                console.log(this.players)
                this.players = _.shuffle(this.players)
            },
        },
        
    }
</script>

<style>
    h5 {
        background-color: yellow;
    }
</style>