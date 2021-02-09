<template>
  <div>
    <a-form
        id="components-form-demo-normal-login"
        :form="form"
        class="login-form"
        @submit.prevent="handleSubmit"
    >
      <a-form-item>
        <a-input
            v-decorator="[
          'userName',
          { rules: [{ required: true, message: '请输入用户名' }] },
        ]"
            placeholder="Username"
        >
          <a-icon slot="prefix" type="user" style="color: rgba(0,0,0,.25)" />
        </a-input>
      </a-form-item>
      <a-form-item>
        <a-input
            v-decorator="[
          'password',
          {
            validateTrigger: ['change', 'blur'],
            rules: [
              { required: true, message: 'Please input your Password!' },
              {min: 6 ,message: '最少6个数字，傻逼啊你'}
          ] },
        ]"
            type="password"
            placeholder="Password"
        >
          <a-icon slot="prefix" type="lock" style="color: rgba(0,0,0,.25)" />
        </a-input>
        <a-button type="primary" html-type="submit" class="login-form-button">
          Log in
        </a-button>
      </a-form-item>
    </a-form>
  </div>
</template>

<script>
export default {
  name: "antdDemo",
  beforeCreate() {
    this.form = this.$form.createForm(this, { name: 'normal_login' });
  },
  methods:{
    handleSubmit() {
      this.form.validateFields((err, values) => {
        if (!err) {
          console.log('Received values of form: ', values);
        }else{
          const {errors} = err.password
          console.log('Received err of form:',err);
          console.log(err.password);
          console.log(errors);
        }
      });
    },
  }
}
</script>

<style scoped>

</style>