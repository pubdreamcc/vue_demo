<template>
  <div id='Item'>
    <ul class="list-group">
      <li class="list-group-item" v-for="(comment,index) of comments" :key='index'>
        <p id="content">{{comment.content}}</p>
        <p id="name">{{comment.name}}</p>
        <button class="btn btn-primary btn01" @click="delComment(index)">删除</button>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'Item',
  data () {
    return {
      
    }
  },
  props: ['comments', 'delData'],
  methods: {
    delComment (i) {
      if (confirm(`确定要删除${this.comments[i].name}的评论吗？`)) {
        this.delData(i)
      }
    }
  }
}
</script>
<style>
#Item li{
  position: relative;
}
#Item #name{
  color: brown;
  font-size: 20px;
}
#Item #content{
  color: deeppink;
  font-size: 28px;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
}
#Item .btn01{
  position: absolute;
  right: 10px;
  bottom: 10px;
} 
</style>
