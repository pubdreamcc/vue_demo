<template>
  <div id="add">
    <form>
      <div class="form-group">
        <label for="name">用户名：</label>
        <input type="text" class="form-control" id="name" placeholder="请输入你的名字：" v-model="name">
      </div>
      <div class="form-group">
        <label for="content">评论：</label>
        <input type="text" class="form-control" id="content" placeholder="请输入你对vue的评论" v-model="content">
      </div>
    </form>
    <button class="btn btn-primary" @click="add">添加</button>
  </div>
</template>
<script>
export default {
  name: 'Add',
  data () {
    return {
      name: '',
      content: ''
    }
  },
  methods: {
    add () {
      if (this.name && this.content) {
        const dataObj = {name: this.name, content: this.content}
        this.comments.unshift(dataObj)
        this.name = this.content = ''
      } else {
        alert('名字或内容不能为空')
      }
    }
  },
  props: ['comments']
}
</script>
<style>
#add{
  border: 1px solid gray;
  position: relative;
  min-height: 300px;
}
#add button{
  position: absolute;
  right: 10px;
  bottom: 10px;
}
</style>
