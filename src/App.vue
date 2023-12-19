<template>
  <div>
    <form @submit.prevent="sendInfo">
      <div>
        <label>Enter a value: </label>
        <input type="text" placeholder="Enter your value" v-model="currValue" @keyup="popUpMessage(currValue)">
      </div>
      <div>
        <h2>List of entered values</h2>
        <ul v-show="listOfvalues.length">
          <li v-for="data, index in listOfvalues" :key="index">
            <p>{{ data }} @ position {{ index }}</p>
          </li>
        </ul>
      </div>
      <button type="submit">Display</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      currValue: '',
      listOfvalues: []
    }
  },
  components: {},
  methods: {
    sendInfo() {
      if (this.currValue)
        this.listOfvalues.push(this.currValue)
    },
    popUpMessage(arg) {
      alert(arg)
    }
  }
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
</style>
