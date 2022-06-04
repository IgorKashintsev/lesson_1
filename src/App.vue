<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld :msg="msg" />
    <p>{{ msg }}</p>
    <!-- <button @click="counter++">{{ counter }}</button> -->
    <!-- <button @click="inc(2, $event)">{{ counter }}</button>
    <button @click="reset">Reset counter</button> -->
    <input type="text" placeholder="text" v-model="someText" @focus="focus" @blur="blur">
    <p>{{ someText }}</p>
    <CalcComponent v-if="show"></CalcComponent>
    <!--<CalcComponent v-if="show" :key="1"></CalcComponent>
    <CalcComponent v-if="!show" :key="2"></CalcComponent>
    <button @click="show = !show">Click</button> -->
    <!-- <div>
      {{ collection }}
    </div>
    <div v-for="(item, index) in collection" :key="index">
      {{ index }}: {{ item }}
    </div>
    <button @click="addElementInCollection">Add</button>
    <button @click="removeElementFromCollection">Remove</button> -->
    <!-- <div v-for="item of arr" :key="item.text" >
      <div v-if="item.show">
        {{ item }}
      </div>
    </div> -->
    <!-- <div v-for="item of filteredArr" :key="item.text" >
      {{ item }}
    </div> -->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import CalcComponent from './components/CalcComponent.vue'

export default {
  name: 'App',
  data() {
    return {
      msg: 'Hello Vue!',
      counter: 0,
      someText: '',
      show: true,
      collection: [1, 2, 3, 4, 5, 6, 7],
      arr: [
        {
          text: 'qwe',
          show: true,
        },
        {
          text: 'rty',
          show: true,
        },
        {
          text: 'asd',
          show: false,
        }
      ]
    }
  },
  methods: {
    inc(step, event) {
      console.log(event);
      this.counter++;
    },
    reset() {
      this.counter = 0;
    },
    focus() {
      console.log('focus');
    },
    blur() {
      console.log('blur');
    },
    addElementInCollection() {
      const nextElementValue = this.collection[this.collection.length - 1] + 1;
      this.collection.push(nextElementValue);
    },
    removeElementFromCollection() {
      this.collection.pop();
    }
  },
  computed: {
    filteredArr() {
      return this.arr.filter(({ show }) => show);
    }
  },
  components: {
    HelloWorld,
    CalcComponent
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
