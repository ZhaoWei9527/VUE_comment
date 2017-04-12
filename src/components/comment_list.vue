<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 v-show="!comments.length">暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
      <item v-for="comment in comments" :comment="comment" :remove-item="removeItem" :index="$index"></item>
    </ul>
  </div>
</template>
<script>
    import item from './item'
    export default{
      props: ['comments', 'removeItem'],
      components: {
        item
      }
    }
</script>
<style>
  .reply {
    margin-top: 0px;
  }
</style>
