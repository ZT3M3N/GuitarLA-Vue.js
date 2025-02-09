<script setup>
import { ref, reactive, onMounted, watch } from "vue";
import { db } from "./data/guitars";
import Guitar from "./components/Guitar.vue";
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";

const guitars = ref([]);
const cart = ref([]);
const guitar = ref({});

watch(
  cart,
  () => {
    saveLocalStorage();
  },
  {
    deep: true,
  }
);

onMounted(() => {
  guitars.value = db;
  guitar.value = db[3];
  const cartStorage = localStorage.getItem("cart");
  if (cartStorage) {
    cart.value = JSON.parse(cartStorage);
  }
});

const saveLocalStorage = () => {
  localStorage.setItem("cart", JSON.stringify(cart.value));
};

const addCart = (guitar) => {
  const existCart = cart.value.findIndex((product) => product.id === guitar.id);

  if (existCart >= 0) {
    cart.value[existCart].quantity++;
  } else {
    guitar.quantity = 1;
    cart.value.push(guitar);
  }
};

const decrementQuantity = (id) => {
  const index = cart.value.findIndex((product) => product.id === id);
  if (cart.value[index].quantity <= 1) return;
  cart.value[index].quantity--;
};

const incrementQuentity = (id) => {
  const index = cart.value.findIndex((product) => product.id === id);
  if (cart.value[index].quantity > 10) return;
  cart.value[index].quantity++;
};

const removeProduct = (id) => {
  cart.value = cart.value.filter((product) => product.id !== id);
};

const removeAllProducts = () => {
  cart.value = [];
};
</script>

<template>
  <Header
    :cart="cart"
    :guitar="guitar"
    @increment-quantity="incrementQuentity"
    @decrement-quantity="decrementQuantity"
    @add-to-cart="addCart"
    @delete-product="removeProduct"
    @remove-all-products="removeAllProducts"
  />
  <body>
    <main class="container-xl mt-5">
      <h2 class="text-center">Nuestra Colección</h2>

      <div class="row mt-5">
        <Guitar v-for="guitar in guitars" :guitar="guitar" @add-to-cart="addCart" />
      </div>
    </main>
    <Footer />
  </body>
</template>
