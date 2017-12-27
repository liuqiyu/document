<template>
  <div class="hello">
    <article class="markdown-body entry-content" itemprop="text" ref="box"></article>
  </div>
</template>

<script>
import marked from 'marked'

var rendererMD = new marked.Renderer()
marked.setOptions({
  renderer: rendererMD,
  gfm: true,
  tables: true,
  breaks: false,
  pedantic: false,
  sanitize: false,
  smartLists: true,
  smartypants: false
}) // 基本设置

export default {
  created () {
    this.$http.get('https://liuqiyu.github.io/docs/VUE/vuex.md').then(response => {
      console.log(response.data)
      console.log(this.$refs.box)
      this.$refs.box.innerHTML = marked(response.data)
      // success callback
    }, response => {
      // error callback
    })
  },
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .hello {
    padding: 20px;
  }
</style>
