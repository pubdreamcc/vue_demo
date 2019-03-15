<template>
  <div id="List">
    <h1>评论展示区</h1>
    <Item :comments='comments' :delData='delData'/>
    <div v-show="comments.length===0" style="color: red;font-size: 35px;">暂时没有评论，请先发表评论</div>
  </div>
</template>
<script>
import Item from './Item'
export default {
  name: 'List',
  props: ['comments', 'delData'],
  components: {
    Item
  }
}
</script>
<style>
#List{
  border: 1px solid gray;
  border-left: none;
}
#List h1{
  color: black;
  font-size: 26px;
  font-weight: 500;
}
</style>
