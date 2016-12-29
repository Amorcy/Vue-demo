<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对React的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <comment-add :add-comment="addComment"></comment-add>
      <comment-list :remove-comment="removeComment" :comments="comments"></comment-list>
    </div>

  </div>
</template>

<script>
  import commentAdd from './commentAdd'
  import commentList from './commentList'
  export default {
    data () {
      return {
        comments: []
      }
    },
    created () {
      this.comments = [
        {
          username: 'Tom',
          content: 'VueJs好难啊!',
          id: Date.now()
        },
        {
          username: 'JACK',
          content: 'VueJS还不错!',
          id: Date.now() + 1
        }
      ]
    },
    components: {commentAdd, commentList},
    methods: {
      addComment (comment) {
        this.comments.unshift(comment)
      },
      removeComment (comment) {
        this.comments.$remove(comment)
      }
    }

  }
</script>

<style>
</style>
