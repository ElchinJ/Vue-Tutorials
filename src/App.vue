<template>
  <div>Hello {{name}}</div>
  <div>He played {{sport}} </div>
  <div v-text="club"></div>
  <div v-html="hack"></div>
  <h3 v-bind:id="headingId">Heading</h3>
  <button v-bind:disabled="isDisabled">Bind</button>
  <p class="underline">Underlined text</p>
  <p class="underline" v-bind:class="status">Dynamic underline text</p>
  <p v-bind:class="isPromoted && 'promoted'">Promoted text</p>
  <p v-bind:class="isSoldout ? 'sold-out' : 'new'">Soldout ? books</p>
  <p v-if="num1 === 0">The number is 0</p>
  <p v-else>The number is not zero</p>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      name: 'Chino',
      sport: "Basketball", 
      club: 'Khatai', 
      hack: `<a href="#" onclick="alert('You have been hacked')">Win a prize</a>`,
      headingId: 'heading',
      isDisabled: true, 
      status: 'danger',
      isPromoted: true,
      isSoldout: true,
      num1: 2,

    };
  },
  // components: {
  //   HelloWorld
  // }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}
.new {
  color: #6b8e23;
}
.sold-out {
  color: red;
}
</style>
