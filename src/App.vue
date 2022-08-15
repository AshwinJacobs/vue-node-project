<template>
  <nav>
    <router-link to="/">HOME</router-link> |
    <div id="inline" v-if="user">
      <router-link to="/products">PRODUCTS</router-link> |
    </div>
    <router-link to="/login">LOGIN</router-link> |
    <router-link to="/register">REGISTER</router-link> |
    <div id="inline" v-if="user">
      <router-link to="/account">ACCOUNT</router-link> |
    </div>
    <div class="bi bi-bag" id="inline" v-if="user">
      <button
        class="btn btn-danger"
        type="button"
        data-bs-toggle="offcanvas"
        data-bs-target="#cartCanvas"
        aria-controls="cartCanvas"
      >
        Cart
      </button>
    </div>
    <div
      class="offcanvas offcanvas-end"
      tabindex="-1"
      id="cartCanvas"
      aria-labelledby="cartCanvasLabel"
    >
      <div class="offcanvas-header">
        <h5 id="cartCanvasLabel">Cart</h5>
        <button
          type="button"
          class="btn-close text-reset"
          data-bs-dismiss="offcanvas"
          aria-label="Close"
        ></button>
      </div>
      <div class="offcanvas-body">
        <Cards v-for="product in cart" :key="product.id" :product="product" />
      </div>
    </div>
  </nav>
  <router-view />
</template>

<script>
import Cards from "./components/Cards.vue";

export default {
  components: { Cards },
  computed: {
    user() {
      return this.$store.state.user;
    },
    cart() {
      return this.$store.state.cart;
    },
  },
};
</script>

<style>
.card {
  border: none;
}

#basket {
  text-decoration: none;
}

#inline {
  display: inline-block;
}

#app {
  font-family: New Century Schoolbook, TeX Gyre Schola, serif;
  font-size: 21px;
  text-align: center;
  color: blue;
  background: rgb(0, 0, 0);
}

nav {
  padding: 5px;
  background-image: url(https://i.postimg.cc/PJBxmyZ7/aurora-1185464-1920.jpg);
  background-size: 100%;
}

nav a {
  font-weight: bold;
  color: white;
  text-decoration: none;
}

#main {
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  min-height: 0vh;
  color: white;
}

nav a.router-link-exact-active {
  color: red;
}
</style>
