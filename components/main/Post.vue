<template>

  <el-card
    shadow="hover"
    :body-style="{padding: 0}"
    class="box-card post"
  >
    <div slot="header" class="post-header">
      <h3>title</h3>
      <small>
        <i class="el-icon-time"></i>
        {{ new Date().toLocaleString() }}
      </small>
    </div>
    <div class="post-img">
      <img src="https://www.zr.ru/_ah/img/abNyQ2_pdVueCiJSp7KbKw=s800" alt="car">
    </div>
    <footer class="post-footer">
      <el-button
        @click="openPost"
        round
      >
        Открыть
      </el-button>
      <span>
        <i class="el-icon-message">
          12
        </i>
      </span>
    </footer>
  </el-card>

</template>

<script>
  export default {
    name: "Post",
    methods: {
      openPost () {
        const id = 'testid'
        this.$router.push(`/post/${ id }`)
      }
    }
  }
</script>

<style lang="scss" scoped>
  .post {
    margin-bottom: 1.5rem;

    &-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    &-img {
      width: 100%;
      height: auto;
    }

    &-footer {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem;
    }
  }

</style>
