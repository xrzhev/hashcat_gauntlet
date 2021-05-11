<template>
  <div class="DictionaryMode">
    <h1>Dictionary Attack Mode</h1>
    <TextArea areaname="hogehoge"/>
    <vue-simple-suggest/>
  </div>
</template>


<script>
import TextArea from '../parts/TextArea.vue'
import VueSimpleSuggest from 'vue-simple-suggest'

export default {
  name: 'AttackMode',
  data: function() {
    return {
      selected_type: "",
      dict_path: ""
    }
  },
  methods: {
    parentcom: function() {
      this.$emit("attack_mode", this.selected_type)
    }
  },
  components: {
    TextArea
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
