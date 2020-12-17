<template>
  <div class="container pt-5 h100">
    <div class="row justify-content-center">
      <div class="col-md-8">
        <!-- début card -->
        <div class="card">
          <div class="card-header bg-theme text-center">
            <h5>Create an account</h5>
          </div>
          <div class="card-body text-center">
            <div class="py-2">
              <div class="form-group row">
                <label for="org-name" class="col-md-4 col-form-label text-md-right"
                  >name of your organisation</label
                >
                <div class="col-md-6">
                  <input
                    v-model="form.name"
                    id="org-name"
                    type="text"
                    class="form-control"
                    required
                    autofocus
                    placeholder="Enter a name..."
                  />
                  <span class="invalid-feedback" role="alert"></span>
                </div>
              </div>
              <div class="form-group row">
                <label for="full-name" class="col-md-4 col-form-label text-md-right"
                  >first and last name</label
                >
                <div class="col-md-6">
                  <input
                    v-model="form.name"
                    id="full-name"
                    type="text"
                    class="form-control"
                    required
                    autofocus
                    placeholder="Enter your full name..."
                  />
                  <span class="invalid-feedback" role="alert"></span>
                </div>
              </div>
              <div class="form-group row">
                <label for="position" class="col-md-4 col-form-label text-md-right"
                  >position within organisation</label
                >
                <div class="col-md-6">
                  <b-dropdown id="dropdown-1" text="choose your position" class="m-md-2">
                    <b-dropdown-item>executing director</b-dropdown-item>
                    <b-dropdown-item>project manager</b-dropdown-item>
                    <b-dropdown-item>M&E officer</b-dropdown-item>
                  </b-dropdown>
                </div>
              </div>
              <div class="form-group row">
                <label for="email" class="col-md-4 col-form-label text-md-right"
                  >email address</label
                >
                <div class="col-md-6">
                  <input
                    v-model="form.email"
                    id="email"
                    type="email"
                    class="form-control"
                    required
                    placeholder="user@example.com"
                  />
                  <span class="invalid-feedback" role="alert"></span>
                </div>
              </div>
              <div class="form-group row">
                <label for="pass1" class="col-md-4 col-form-label text-md-right"
                  >password</label
                >
                <div class="col-md-6">
                  <input
                    v-model="form.password"
                    id="pass1"
                    type="password"
                    class="form-control"
                    required
                  />
                  <span class="invalid-feedback" role="alert"></span>
                </div>
              </div>
              <div class="form-group row">
                <label for="pass2" class="col-md-4 col-form-label text-md-right"
                  >confirm password</label
                >
                <div class="col-md-6">
                  <input
                    v-model="form.password2"
                    id="pass2"
                    type="password"
                    class="form-control"
                    required
                  />
                  <span class="invalid-feedback" role="alert"></span>
                </div>
              </div>
              <button
                type="submit"
                @click="register"
                class="btn btn-primary my-4"
              >
                create your account
              </button>
            </div>
          </div>
        </div>
        <!-- *********** fin card *************-->
      </div>
    </div>
  </div>
</template>

<script>
//import User from "../apis/User";

export default {
  data: () => ({
    errors: "",
    error_message: "",
    form: {
      name: "",
      email: "",
      password: "",
      password2: "",
    },
  }),

  watch: {},

  methods: {
    toast(title, message, faulty = false) {
      this.$root.$bvToast.toast(message, {
        title: title,
        toaster: "b-toaster-top-center",
        variant: faulty ? "danger" : "success",
        appendToast: true,
      });
    },
    /*register() {
      if (
        this.form.org-name &&
        this.form.full-name &&
        this.form.position &&
        this.form.email &&
        this.form.password &&
        this.form.password2
      ) {
        if (this.form.password == this.form.password2) {
          //const bcrypt = require("bcrypt"); //
          //const hashedPwd = bcrypt.hash(password, 10); //
          //this.form.password = hashedPwd; //
          User.register(this.form)
            .then((response) => {
              console.log("res data", response.data);
              if (response.data.error) {
                this.toast("Error!", response.data.error, true);
              } else {
                this.$router.push({ name: "Login" });
              }
            })
            .catch((error) => {
              this.toast("Error!", error.message, true);
            });
        } else {
          this.toast(
            "Error!",
            "Password and password confirmation have to be identical",
            true
          );
        }
      } else {
        this.toast("error!", "All fields have to be filled", true);
      }
    },*/
  },
};
</script>
