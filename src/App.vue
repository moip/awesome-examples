<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h2> Awesome Mask </h2>
    <p>The awesome-mask runs with Vue.js and uses the vanilla-masker to make your form awesome with masks.</p>
    <h3>Installation</h3>
    <code>
        npm i --save awesome-mask
    </code>
    <h3>Contribute</h3>
    <a href="https://github.com/moip/awesome-mask"> GitHub </a>
    <div class="mdl-textfield mdl-js-textfield">
      <input v-mask="'AAA-9999'" class="mdl-textfield__input" type="text" id="sample1">
      <label class="mdl-textfield__label" for="sample1">Car Plate</label>
    </div>
    <code>
        &lt; input type="text" v-mask="'AAA-9999'" &gt;
    </code>
    <div class="mdl-textfield mdl-js-textfield">
      <input v-mask="'999.999.999-99'" class="mdl-textfield__input" type="text" id="sample2">
      <label class="mdl-textfield__label" for="sample2">CPF</label>
    </div>
    <code>
        &lt; input type="text" v-mask="'999.999.999-99'" &gt;
    </code>
    <div class="mdl-textfield mdl-js-textfield">
      <input v-mask="'money'" class="mdl-textfield__input" type="text" id="sample4">

      <label class="mdl-textfield__label" for="sample4">Money</label>
    </div>
    <code>
        &lt; input type="text" v-mask="'money'" &gt;
    </code>


    <div class="mdl-textfield mdl-js-textfield">
      <input @input="bla" type="text" class="mdl-textfield__input" v-model="price" id="sample5" v-mask="'money'">
      <label class="mdl-textfield__label" for="sample5">Money with v-model</label>
    </div>
    <code>
        &lt; input  v-model="price type="text" v-mask="'money'" &gt;
    </code>

    <div class="mdl-textfield mdl-js-textfield">
      <input v-mask="'99/99/9999'" class="mdl-textfield__input" type="text" id="sample3">
      <label class="mdl-textfield__label" for="sample3">Date</label>
    </div>
    <code>
        &lt; input type="text" v-mask="'99/99/9999'" &gt;
    </code>
    <div class="mdl-textfield mdl-js-textfield">
      <input v-mask="mask" @input="_updateMask" class="mdl-textfield__input" type="text" id="sample3">
      <label class="mdl-textfield__label" for="sample3">TaxDocument</label>
    </div>
    <p>HTML</p>
    <code>
        &lt; input v-mask="mask" @input="_updateMask" &gt;
    </code>
    <p>Vue.js</p>
    <code>
      methods: {
        _updateMask (ev) {
          console.log(ev.target.value)
          if (ev.target.value.length > 14) {
            this.mask = '99.999.999/9999-99'
          } else {
            this.mask = '999.999.999-999'
          }
        }
      }
    </code>
  </div>
</template>

<script>
import Hello from './components/Hello'
import AwesomeMask from 'awesome-mask'

export default {
  name: 'app',
  components: {
    Hello
  },
  data () {
    return {
      mask: '999.999.999-99',
      price: -20
    }
  },
  methods: {
    _updateMask (ev) {
      console.log(ev.target.value)
      if (ev.target.value.length > 14) {
        this.mask = '99.999.999/9999-99'
      } else {
        this.mask = '999.999.999-999'
      }
    },
    bla (ev) {
      // console.log(ev.target.value)
    }
  },
  directives: {
    'mask': AwesomeMask
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.mdl-textfield{
  display: block !important;
  margin: 0 auto !important;;
}
code {
  display: inline-block;
  white-space: pre-wrap;
  text-align: left;
  margin: 0 auto;
  background-color: #f2f2f2;
  padding-right: 3em;
  border-radius: 2px;
}
</style>
