<template>
  <div class="handle">
    <a href="javascript:;" @click="handleA">删除</a>
  </div>
  <p class="user"><span v-text="comment.username"></span><span>说:</span></p>
  <p class="centence" v-text="comment.content"></p>
</template>

<script>
  export default {
    props: {
      comment: {
        type: Object
      },
      removeComment: {
        type: Function
      }
    },
    methods: {
      handleA () {
        let username = this.comment.username
        if (confirm(`确定要删除${username}吗？`)) {
          this.removeComment(this.comment)
        }
      }
    }
  }
</script>

<style>
  li {
    transition: .5s;
    overflow: hidden;
  }

  .handle {
    width: 40px;
    border: 1px solid #ccc;
    background: #fff;
    position: absolute;
    right: 10px;
    top: 1px;
    text-align: center;
  }

  .handle a {
    display: block;
    text-decoration: none;
  }

  .list-group-item .centence {
    padding: 0px 50px;
  }

  .user {
    font-size: 22px;
  }
</style>
