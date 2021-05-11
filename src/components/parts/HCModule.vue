<template>
  <div class="hashcat_module">
    <input type="text" name="selected_module" list="suggest_module" v-model="selected_module">
    <datalist id="suggest_module">
      <option v-for="module in modules" :key="module.name" :value="module.name"/>
    </datalist>
  </div>
  <Notification v-if="selected_module" :text="selected_module"/>
</template>


<script>
import Notification from './Notification.vue'
export default {
  name: 'HCModule',
  data: function() {
    return {
      selected_module: "",
      modules: null,
      hover: false
    }
  },
  methods: {
    parentcom: function() {
      this.$emit("text", this.text)
    },
    isMouseOver: function() {
      this.hover = true
    },
    isMouseLeave: function() {
      this.hover = true
    }
  },
  mounted() {
      fetch(location.protocol + "//" + location.host + "/modules.json")
      .then(resp => resp.json())
      .then(data => (this.modules = data))
  },
  components: {
    Notification
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
