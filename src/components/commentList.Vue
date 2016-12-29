<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 v-show="comments.length===0">暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
      <li v-for="comment in comments" class="list-group-item">
        <comment-item :comment="comment" :remove-comment="removeComment"></comment-item>
      </li>
    </ul>
  </div>
</template>

<script>
  import commentItem from './commentItem'
  export default {
    props: {
      comments: {
        type: Array
      },
      removeComment: {
        type: Function
      }
    },
    components: {commentItem}
  }
</script>

<style>
  .reply {
    margin-top: 0px;
  }
</style>
