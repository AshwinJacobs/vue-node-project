<template>
  <div id="main">
    <div class="container">
      <div class="row justify-content-center">
        <div id="registerzone" class="col-lg-4 col-md-6 col-sm-6">
          <h2 class="">Register Your Account</h2>
          <div id="cardzone" class="card shadow text-white">
            <div class="card-title text-center text-white border-bottom">
              <h2>Register</h2>
            </div>
            <div class="card-body text-white">
              <form method="POST" @submit="registerUser">
                <div class="mb-4">
                  <label for="firstName" class="form-label">First Name</label>
                  <input
                    v-model="firstName"
                    type="text"
                    class="form-control"
                    name="firstName"
                  />
                </div>
                <div class="mb-4">
                  <label for="address" class="form-label"
                    >Billing_Address</label
                  >
                  <input
                    v-model="address"
                    type="text"
                    class="form-control"
                    name="address"
                  />
                </div>
                <div class="mb-4">
                  <label for="phoneNumber" class="form-label">Phone</label>
                  <input
                    v-model="phoneNumber"
                    type="number"
                    class="form-control"
                    name="phoneNumber"
                  />
                </div>
                <div class="mb-4">
                  <label for="email" class="form-label">Email</label>
                  <input
                    type="email"
                    v-model="email"
                    class="form-control"
                    name="email"
                  />
                </div>
                <div class="mb-4">
                  <label for="password" class="form-label">Password</label>
                  <input
                    v-model="userPassword"
                    type="password"
                    class="form-control"
                    name="password"
                  />
                </div>
                <div class="d-grid">
                  <button type="submit" req class="btn bg-danger text-white">
                    Register
                  </button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstName: null,
      Billing_address: null,
      cart: null,
      Number: null,
      email: null,
      Password: null,
    };
  },
  methods: {
    registerUser(event) {
      event.preventDefault();
      const user = {
        firstName: this.firstName,
        Billing_address: this.Billing_address,
        cart: this.cart,
        phone: this.phone,
        email: this.email,
        Password: this.Password,
      };
      this.$store.dispatch("registerUser", user);
    },
  },
};
</script>

<style scoped>
#main {
  background-image: url(https://i.postimg.cc/kGzK6nDx/galaxy-11098.jpg);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  height: 100%;
  color: white;
}

#registerzone {
  padding: 50px 0 50px 0;
}

#cardzone {
  padding: 40px 50px 40px 50px;
  border-radius: 20px;
  background-color: transparent;
}

.card,
.btn,
input {
  border-radius: 0;
}
input {
  background-color: black;
  color: aliceblue;
}
</style>
