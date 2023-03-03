<template>
  <div class="card-back">
    <div class="center-wrap">
      <div class="section text-center">
        <h4 class="mb-4 pb-3">Sign Up</h4>
        <div class="row">
          <div class="col-md-6">
            <div class="form-group">
              <input
                type="text"
                name="logname"
                class="form-style"
                placeholder="Your Full Name"
                id="logname"
                autocomplete="off"
                v-model="name"
              />
              <i class="input-icon uil uil-user"></i>
            </div>
          </div>
          <div class="col-md-6">
            <div class="form-group mt-2">
              <input
                type="email"
                name="logemail"
                class="form-style"
                placeholder="Your Email"
                id="logemail"
                autocomplete="off"
                 v-model="email"
              />
              <i class="input-icon uil uil-at"></i>
            </div>
          </div>
          <div class="col-md-6">
            <div class="form-group mt-2">
              <input
                type="password"
                name="logpass"
                class="form-style"
                placeholder="Your Password"
                id="logpass"
                autocomplete="off"
                 v-model="password"
              />
              <i class="input-icon uil uil-lock-alt"></i>
            </div>
          </div>
          <div class="col-md-6">
            <div class="form-group mt-2">
              <input
                type="password"
                name="logpass"
                class="form-style"
                placeholder="confirm password"
                id="logpass"
                autocomplete="off"
                v-model="confirmPassword"
              />
              <i class="input-icon uil uil-lock-alt"></i>
            </div>
          </div>
          <div class="col-md-6 mt-2">
            <select
            v-model="selcshen"
              class="form-select form-select-lg"
              aria-label=".form-select-lg example"
            >
              <option selected value="">Open this select menu</option>
              <option value="1">kish</option>
              <option value="2">tehran</option>
              <option value="3">ahvaz</option>
            </select>
          </div>
          <div class="col-md-6">
            <div class="form-group mt-3">
              <label for="1">mester</label>
              <input type="radio" name="jander" class="m-2" value="mester" v-model="role"/>
              <label for="2">miss</label>
              <input
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

        <button href="#" class="btn mt-4" @click="register()">submit</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name:"",
      email:"",
      password:"",
      confirmPassword:"",
      role:"",
      selcshen:""
    }
  },
  methods:{
    register(){
      console.log(this.name);
      console.log(this.email);
      console.log(this.password);
      console.log(this.confirmPassword);
      console.log(this.role);
      console.log(this.selcshen);
    }
  }
}
</script>