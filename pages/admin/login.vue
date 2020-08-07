<template>
  <el-card
    shadow="always"
    :style="{width: '500px'}"
  >
    <el-form
      :model="controls"
      :rules="rules"
      ref="form"
      @submit.native.prevent="onSubmit"
    >
      <h1>Добавить комментарий</h1>

      <el-form-item label="Логин" prop="login">
        <el-input
          v-model.trim="controls.name"
        />
      </el-form-item>

      <el-form-item label="Пароль" prop="password">
        <el-input
          v-model.trim="controls.text"
          type="password"
        />
      </el-form-item>

      <el-form-item>
        <el-button
          type="primary"
          native-type="submit"
          round
          :loading="loading"
        >
          Добавить комментарий
        </el-button>
      </el-form-item>
    </el-form>

  </el-card>
</template>

<script>
  export default {
    name: "login",
    layout: "empty",
    data () {
      return {
        controls: {
          login: '',
          password: '',
        },
        rules: {
          login: [
            { required: true, message: 'Логин не должен быть пустым', trigger: 'blur' },
          ],
          password: [
            { required: true, message: 'Введите ваш комментарий', trigger: 'blur' }
          ],
        }
      }
    },
    methods: {
      onSubmit () {
        console.log('Submit')
      }
    },
  }
</script>

<style lang="scss" scoped>

</style>
