<template>
  <div class="card-front">
    <div class="center-wrap">
      <div class="section text-center">
        <Form @submit="Login" :validation-schema="loginformschema">
          <h4 class="mb-4 pb-3">Log In</h4>
          <div class="form-group">
            <Field
              type="text"
              class="form-style"
              placeholder="Your Email"
              id="logemail"
              autocomplete="off"
              name="email"
              :validate-on-input="true"
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
              :validate-on-input="true"
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
import * as yup from "yup";
export default {
  components: { Field, Form, ErrorMessage },
  data() {
    const loginformschema = yup.object({
      email: yup
        .string()
        .required("ایمیل را وارد کنید")
        .email("ایمیل نامعتبر است"),
      password: yup
        .string()
        .required("کلمه عبور را وارد کنید")
        .min(5, "کلمه عبور باید بیشتر از 5 کارکتر باشد"),
    });
    return {
      loginformschema,
    };
  },
  methods:{
    Login(valus){
      console.log(valus);
    }
  }
};
</script>

<style>
</style>