<template>
  <el-form
    :model="controls"
    :rules="rules"
    ref="form"
    @submit.native.prevent="onSubmit"
  >
    <h1>Добавить комментарий</h1>

    <el-form-item label="Ваше Имя" prop="name">
      <el-input
        v-model.trim="controls.name"
      />
    </el-form-item>

    <el-form-item label="Текст комментария" prop="text">
      <el-input
        type="textarea"
        resize="none"
        :rows="3"
        v-model.trim="controls.text"
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
</template>

<script>
  export default {
    name: "CommentForm",
    data () {
      return {
        loading: false,
        controls: {
          name: '',
          text: '',
        },
        rules: {
          name: [
            { required: true, message: 'Имя не должно быть пустым', trigger: 'blur' },
          ],
          text: [
            { required: true, message: 'Введите ваш комментарий', trigger: 'blur' }
          ],
        }
      }
    },
    methods: {
      onSubmit () {
        this.$refs.form.validate(valid => {
          if (valid) {
            this.loading = true
            const formData = {
              name: this.controls.name,
              text: this.controls.text,
              postId: ''
            }
            try {
              this.$message.success('Комментарий добавлен')
              this.$emit('created')
            } catch (e) {
              console.log(e)
            }
          }
        })
      },
    },

  }
</script>

<style lang="scss" scoped>

</style>
