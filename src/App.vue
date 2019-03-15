<template>
  <div id="app">
    <h1>请发表对vue的评论</h1>
    <div class="container">
      <div class="row">
        <Add class="col-md-4" :comments='comments'/>
        <List class="col-md-8" :comments='comments' :delData='delData'/>
      </div>
    </div>
  </div>
</template>

<script>
import Add from './components/Add'
import List from './components/List'
export default {
  name: 'App',
  data () {
    return {
      comments: [
        {name: 'Bom', content: 'Vue is so easy'},
        {name: 'Tom', content: 'Vue so so'},
        {name: 'Jack', content: 'Vue easy to study'},
        {name: 'Lily', content: 'Vue 很好玩，快来学'}
      ]    
    }
  },
  components: {
    List,
    Add
  },
  methods: {
    delData (index) {
      this.comments.splice(index, 1)
    }
  }
}
</script>

<style>
#app > h1{
  height: 100px;
  box-sizing: content-box;
  padding: 20px 0 0 40px;
  background: gray;
  color: #bbffaa;
  font-size: 32px;
  font-weight: 600;
  margin-bottom: 50px;
}
</style>
