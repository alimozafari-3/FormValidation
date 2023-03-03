<template>
  <div class="card-front">
    <div class="center-wrap">
      <div class="section text-center">
        <Form @submit="Login">
          <h4 class="mb-4 pb-3">Log In</h4>
          <div class="form-group">
            <Field
              type="text"
              class="form-style"
              placeholder="Your Email"
              id="logemail"
              autocomplete="off"
              name="email"
              :rules="emailrul"
            />
            <i class="input-icon uil uil-at"></i>
          </div>
          <p class="text-danger"><ErrorMessage name="email" /></p>
          <div class="form-group mt-2">
            <Field
              type="password"
              class="form-style"
              placeholder="Your Password"
              id="logpass"
              autocomplete="off"
              name="password"
              :rules="passwordrul"
            />
            <i class="input-icon uil uil-lock-alt"></i>
          </div>
          <p class="text-danger"><ErrorMessage name="password" /></p>
          <button class="btn mt-4">submit</button>
          <p class="mb-0 mt-4 text-center">
            <a href="#0" class="link">Forgot your password?</a>
          </p>
        </Form>
      </div>
    </div>
  </div>
</template>

<script>
import { Field, Form, ErrorMessage } from "vee-validate";
import * as yup from 'yup'
export default {
  components: { Field, Form, ErrorMessage },
  data() {
    return {
      emailrul: yup.string().required("ایمیل را وارد کنید").email("ایمیل نامعتبر است"),
      passwordrul: yup.string().required("کلمه عبور را وارد کنید").min(5,'کلمه عبور باید بیشتر از 5 کارکتر باشد'),
    };
  },
  methods: {
    Login(values) {
      console.log(values);
    },
   
    
  },
};
</script>

<style>
</style>