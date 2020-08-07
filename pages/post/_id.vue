<template>
  <article class="post">

    <header class="post-header">
      <div class="post-title">
        <h1>Post title</h1>
        <nuxt-link to="/">
          <i class="el-icon-back"></i>
        </nuxt-link>
      </div>

      <div class="post-info">
        <small>
          <i class="el-icon-time"></i>
          {{ new Date().toLocaleString() }}
        </small>
        <small class="post-view">
          <i class="el-icon-view"></i>
          42
        </small>
      </div>

      <div>
        <img class="post-image" src="https://www.zr.ru/_ah/img/abNyQ2_pdVueCiJSp7KbKw=s800" alt="car">
      </div>
    </header>

    <main class="post-content">
      <h3>Post content</h3>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Asperiores assumenda consequatur corporis, culpa cum cupiditate dignissimos distinctio ex id ipsam, iure libero nisi nostrum porro quos reiciendis sed velit veniam!</p>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Asperiores assumenda consequatur corporis, culpa cum cupiditate dignissimos distinctio ex id ipsam, iure libero nisi nostrum porro quos reiciendis sed velit veniam!</p>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Asperiores assumenda consequatur corporis, culpa cum cupiditate dignissimos distinctio ex id ipsam, iure libero nisi nostrum porro quos reiciendis sed velit veniam!</p>
    </main>

    <footer>
      <app-comment-form
        v-if="canAddComment"
        @created="creatCommentHandler"
      />

      <div class="comments" v-if="false">
        <app-comments
          v-for="comment in 4"
          :key="comment"
          :comment="comment"
        />
      </div>

      <div class="text-center" v-else>Комментариев нет</div>
    </footer>
  </article>
</template>

<script>
  import AppComments from '@/components/main/Comment';
  import AppCommentForm from '@/components/main/CommentForm';

  export default {
    components: { AppComments, AppCommentForm },
    validate ({ params }) {
      return Boolean(params.id)
    },
    data () {
      return {
        canAddComment: true
      }
    },
    methods: {
      creatCommentHandler () {
        setTimeout(() => {this.canAddComment = false}, 1000)
      }
    },
  }
</script>

<style lang="scss" scoped>
  .post {
    max-width: 600px;
    margin: 0 auto;

    &-title {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 0.5rem;
    }

    &-image {
      width: 100%;
      height: auto;
    }

    &-header {
      margin-bottom: 1.5rem;
    }

    &-view {
      margin-left: 10px;
    }

    &-content {
      margin-bottom: 2rem;
    }
  }
</style>
