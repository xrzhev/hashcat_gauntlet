<template>
  <h1>hashcat_gauntlet</h1>
  <h3>Related version: {{ rerated_version }}</h3>
  <AttackMode @attack_mode='attack_mode = $event'/>
  <br>
  <HCModule/>
  <br>
  <Dictionary v-if="attack_mode.name === 'Dictionary'"/>
  <br>
  <br>
  <br>
  {{ payload }}
</template>

<script>
import AttackMode from './components/AttackMode.vue'
import HCModule   from './components/parts/HCModule.vue'
import Dictionary from './components/Attack/Dictionary.vue'

import '../node_modules/bulma/css/bulma.min.css'
import VueSimpleSuggest from 'vue-simple-suggest'

export default {
  name: 'App',
  data: function() {
    return {
      attack_mode: "",
      payload: "hashcat "
      }
  },
  computed: {
     rerated_version: () => "Hashcat v6.1.1"
  },
  components: {
    AttackMode,
    Dictionary,
    HCModule,
    VueSimpleSuggest,
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
  #margin-top: 60px;
}
</style>
