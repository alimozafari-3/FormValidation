<template>
  <div class="card-back">
    <div class="center-wrap">
      <Form @submit="register()">
        <div class="section text-center">
          <h4 class="mb-4 pb-3">Sign Up</h4>
          <div class="row">
            <div class="col-md-6">
              <div class="form-group">
                <Field
                  type="text"
                  class="form-style"
                  placeholder="Your Full Name"
                  id="logname"
                  autocomplete="off"
                  name="name"
                  :rules="name"
                  :validate-on-input="true"
                />
                <i class="input-icon uil uil-user"></i>
              </div>
              <p class="text-danger"><ErrorMessage name="name" /></p>
            </div>
            <div class="col-md-6">
              <div class="form-group mt-2">
                <Field
                  type="email"
                  class="form-style"
                  placeholder="Your Email"
                  id="logemail"
                  autocomplete="off"
                  name="email"
                  :rules="email"
                  :validate-on-input="true"
                />
                <i class="input-icon uil uil-at"></i>
              </div>
              <p class="text-danger"><ErrorMessage name="email" /></p>
            </div>
            <div class="col-md-6">
              <div class="form-group mt-2">
                <Field
                  type="password"
                  class="form-style"
                  placeholder="Your Password"
                  id="logpass"
                  autocomplete="off"
                  name="password"
                  :rules="password"
                  :validate-on-input="true"
                />
                <i class="input-icon uil uil-lock-alt"></i>
              </div>
              <p class="text-danger"><ErrorMessage name="password" /></p>
            </div>
            <div class="col-md-6">
              <div class="form-group mt-2">
                <Field
                  type="password"
                  class="form-style"
                  placeholder="confirm password"
                  id="logpass"
                  autocomplete="off"
                  name="confirmPassword"
                  :rules="confirmPassword"
                  :validate-on-input="true"
                />
                <i class="input-icon uil uil-lock-alt"></i>
              </div>
              <p class="text-danger"><ErrorMessage name="confirmPassword" /></p>
            </div>
            <div class="col-md-6 mt-2">
              <Field
                as="select"
                name="selcshen"
                :rules="selcshen"
                :validate-on-input="true"
                class="form-select form-select-lg"
                aria-label=".form-select-lg example"
              >
                <option selected value="">Open this select menu</option>
                <option value="1">kish</option>
                <option value="2">tehran</option>
                <option value="3">ahvaz</option>
              </Field>
              <p class="text-danger"><ErrorMessage name="selcshen" /></p>
            </div>
            <div class="col-md-6">
              <div class="form-group mt-3">
                <label for="1">mester</label>
                <Field
                  type="radio"
                  name="jander"
                  class="m-2"
                  value="mester"
                  v-model="role"
                />
                <label for="2">miss</label>
                <Field
                  type="radio"
                  name="jander"
                  class="m-2"
                  id="2"
                  value="miss"
                  v-model="role"
                />
              </div>
            </div>
          </div>

          <button href="#" class="btn mt-4">submit</button>
        </div>
      </Form>
    </div>
  </div>
</template>

<script>
import { Field, Form, ErrorMessage } from "vee-validate";
import * as yup from "yup";
export default {
  components: { Field, Form, ErrorMessage },
  data() {
    return {
      name: yup.string().required("اسم خود را وارد کنید"),
      email: yup
        .string()
        .required("ایمیل خود را وارد کنید")
        .email("ایمیل نامعتر است"),
      password: yup
        .string()
        .required("پسورد خود را وارد کنید")
        .min(6, "پسورد نباید کمتر از 6 کاراکتر باشد"),
      confirmPassword: yup
        .string()
        .required()
        .oneOf([yup.ref("password")], "Passwords do not match"),
      selcshen: yup.string().required(),
    };
  },

  methods: {
    register(valus) {
   console.log(valus);
    },
  },
};
</script>