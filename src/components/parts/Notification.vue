<template>
  <div class="notification is-primary">
    <button class="delete"></button>
    {{ text }}
  </div>
</template>


<script>
export default {
  name: 'TextArea',
  data: function() {
    return {
    }
  },
  props: {
    text: String
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
