<template>
  <div class="attack_modes">
    <h1>Select Attack mode</h1>
    <div class="attack_mode" v-for="attack_type in attack_types" :key="attack_type.name">
      <label>
      <input type="radio" name="attack_type" v-bind:value="attack_type" v-model="selected_type" @change="parentcom">
      {{ attack_type.name }} Attack
      </label>
    </div>
  </div>
</template>


<script>
export default {
  name: 'AttackMode',
  data: function() {
    return {
      selected_type: ""
    }
  },
  computed: {
    attack_types: () => [
        {id: 0, name: "Dictionary"},
        {id: 1, name: "Combinator"},
	{id: 2, name: "Brute-Force"},
	{id: 3, name: "Hybrid"} ]
  },
  methods: {
    parentcom: function() {
      this.$emit("attack_mode", this.selected_type)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
