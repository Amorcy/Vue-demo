<template>
  <div class="col-md-4">
    <form class="form-horizontal">
      <div class="form-group">
        <label>用户名</label>
        <input type="text" v-model="comment.username" class="form-control" placeholder="用户名">
      </div>
      <div class="form-group">
        <label>评论内容</label>
        <textarea v-model="comment.content" class="form-control" rows="6" placeholder="评论内容"></textarea>
      </div>
      <div class="form-group">
        <div class="col-sm-offset-2 col-sm-10">
          <button type="button" @click="handleSubmit" class="btn btn-default pull-right">提交</button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
  export default {
    props: {
      addComment: {
        type: Function
      }
    },
    data () {
      return {
        comment: {}
      }
    },
    methods: {
      handleSubmit() {
        let comment = this.comment
        comment.id = Date.now()
        this.addComment(comment)
        this.comment = {}
      }
    }

  }
</script>

<style>
</style>
