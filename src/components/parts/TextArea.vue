<template>
  <div class="userinputtext">
    <textarea v-bind:name="areaname" v-model="input_text">
    </textarea>
    <!--@change:"parentcom">-->
  </div>
  {{ input_text }}
</template>


<script>
export default {
  name: 'TextArea',
  data: function() {
    return {
      input_text: ""
    }
  },
  props: {
    areaname: String
  },
  methods: {
    parentcom: function() {
      this.$emit("text", this.text)
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
