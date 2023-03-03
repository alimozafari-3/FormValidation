<template>
  <div>
   
  <a href="https://front.codes/" class="logo" target="_blank">
    <img src="https://assets.codepen.io/1462889/fcy.png" alt="">
  </a>

  <div class="section">
    <div class="container">
      <div class="row full-height justify-content-center">
        <div class="col-12 text-center align-self-center py-5">
          <div class="section pb-5 pt-5 pt-sm-2 text-center">
            <h6 class="mb-0 pb-3"><span>Log In </span><span>Sign Up</span></h6>
                  <input class="checkbox" type="checkbox" id="reg-log" name="reg-log"/>
                  <label for="reg-log"></label>
            <div class="card-3d-wrap mx-auto">
              <div class="card-3d-wrapper">
                <app-register></app-register>
                    <app-login></app-login>
                  </div>
                </div>
              </div>
            </div>
          </div>
      </div>
  </div>
  </div>
</template>

<script>
import login from './components/login-L.vue'
import register from './components/Register-Re.vue'
export default {
  components:{"app-login":login,"app-register":register}
};
</script>

<style>
</style>
