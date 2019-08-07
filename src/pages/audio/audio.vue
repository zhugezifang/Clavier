<template>
  <main class="page-audio">
    <header class="">Audio demo</header>
    <section id="testAudio">
      原文: {{paraText}}
    </section>

    <section>
      计算后: 
      <p v-for="(item, index) in paraArr" :key="index">{{item}}</p>
    </section>
  </main>
</template>

<script>
import Vue from 'vue'
import { DemoText } from 'config/'
export default {
  name: 'Audio',
  data() {
    return {
      paraText: DemoText.para,
      paraArr: [],
      inputText: ''
    }
  },
  mounted() {
    console.log(DemoText)
    this.paraArr = this.computedText().map(item => this.computedItem(item))
  },
  methods: {
    formatSyllable (n) {
      return `1 / ${2 ^ n}`
    },
    computedText() {
      let input = this.input && this.input != void 0 && this.input != '' ? this.input : DemoText.para
      let arr = input.replace(/\n/g, ' ').replace(/\?|!|'|:|,/g, '').split(' ')
      let paraArr = arr.map(element => {
        return element.toString().toLowerCase()
      })
      console.log(paraArr)
      console.log(this.paraArr)
      return paraArr
      // 格式化数组
    },
    computedItem(text) {
      return text.split('')
    }
  },
}
</script>

<style lang="less">
@pblue: #1296db;
@textdark: #2c3e50;
.page-audio { 
  width: 100%; min-width: 1080px; min-height: 100%; padding: 1px; padding-bottom: 150px; font-family: 'Avenir', Helvetica, Arial, sans-serif; -webkit-font-smoothing: antialiased; -moz-osx-font-smoothing: grayscale; color: @textdark; font-weight: bold; position: absolute; top: 0; left: 0;
  header, section {
    padding: 16px;
  }
  header {
    font-size: 20px;
  }
}
</style>