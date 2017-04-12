<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对Vue的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <comment-add :add-item="addItem"></comment-add>
      <comment-list :comments="comments" :remove-item="removeItem"></comment-list>
    </div>
  </div>
</template>
<script>
    import commentAdd from './components/comment_add'
    import commentList from './components/comment_list'
    export default{
      data () {
        return {
          comments: []
        }
      },
      methods: {
        addItem (todo) {
          this.comments.unshift(todo)
        },
        removeItem (index) {
          this.comments.splice(index, 1)
        }
      },
      created () {
        setTimeout(() => {
          this.comments = [
            {name: 'xxxx', content: 'vue还挺好用'},
            {name: 'yyyy', content: '确实，虽然不懂，但感觉很牛逼'}
          ]
        }, 1000)
      },
      events: {
        'remove': function (comment) {
          console.log(comment)
          this.comments.$remove(comment)
        }
      },
      components: {
        commentAdd,
        commentList
      }
    }
</script>
<style scoped>

</style>
