<template>
  {{ greet }} {{ name }} {{ channel }}
  <div v-html="htm"></div>
  <div v-bind:id="headingId">Heading</div>
  <button v-bind:disabled="isDisabled">Bind</button>
  <button @click="sch">Toggle</button>
  <h2 class="underlined">underlined text</h2>
  <h2 v-bind:class="isPromoted && 'promoted'" class="underline ">Test de class bind </h2>
  <ul>
    <li v-for="(name, index) in names" :key="name">{{ index + 1 }}. {{ name }}</li>
  </ul>
  <h3 v-for="(fullname,index) in fullnames" :key="fullname.last">{{ index }}. {{ fullname.first }}  {{ fullname.last }}</h3>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data() {
    return {
      name: "cata",
      greet: "ciao",
      channel: "test",
      htm: `<a href="#"  onclick="alert('hacked')" > click the  link </a>`,
      headingId: 'heading',
      isDisabled: true,
      status: "success",
      isPromoted: true,
      names: ['test 1', 'test2', 'test3'],
      fullnames: [
        { 'first': 'Catalin', 'last': 'Arsulescu' },
        { 'first': 'Cezar', 'last': 'Bolintineanu' },
        { 'first': 'Alexandre', 'last': 'Dumas' },
      ],
    };
  },
  methods: {
    sch() {
      this.isDisabled = !this.isDisabled
    }, shuffle(){
      this.fullnames = 
    }
  },
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

.underlined {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}
</style>
