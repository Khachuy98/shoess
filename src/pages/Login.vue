<template>
  <div class="loginform">
    <b-container>
      <b-row class="justify-content-md-center mt-4">
        <b-col col md="5">
          <h2>Login Shoes Store</h2>
          <!-- <b-card header="Login - Shoes Store"
          header-bg-variant="primary"
          header-text-variant="white">
          </b-card> -->
          <b-card-text>
            <form>
              <b-form-group description="Enter your email" label="Email">
                <b-form-input
                  v-model="email"
                  required
                  type="email"
                ></b-form-input>
              </b-form-group>
              <b-form-group description="Enter your password" label="Password">
                <b-form-input
                  v-model="password"
                  required
                  type="password"
                ></b-form-input>
              </b-form-group>
              <b-form-group>
                <b-button
                  block
                  variant="primary"
                  type="submit"
                  :disabled="acceptableSubmittion"
                  @click.prevent="clickSubmit"
                  >Login</b-button
                >
              </b-form-group>
            </form>
          </b-card-text>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: ""
    };
  },
  methods: {
    // onSubmit(event) {
    //   event.preventDefault()
    //   alert('Login succsesfully')
    // },
    clickSubmit() {
      var data = {
        email: this.email,
        password: this.password
      };
      alert("Login succsesfully");
      this.$router.push('/admin');
    }
  },
  computed: {
    acceptableSubmittion() {
      return this.email.length > 0 && this.password > "" ? false : true;
    }
  }
};
</script>

<style scoped>
h2 {
  text-align: center;
  text-transform: uppercase;
  font-weight: bolder;
}
.btnlogin {
  margin: -50px 172px;
  padding: 10px 40px;
}
</style>
