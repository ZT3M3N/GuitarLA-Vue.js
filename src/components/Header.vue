<script setup>
import { computed } from "vue";
const props = defineProps({
  cart: {
    type: Array,
    required: true,
  },
  guitar: {
    type: Object,
    required: true,
  },
});

defineEmits([
  "decrement-quantity",
  "increment-quantity",
  "add-to-cart",
  "delete-product",
  "remove-all-products",
]);

const totalPayment = computed(() => {
  return props.cart.reduce(
    (total, product) => total + product.quantity * product.price,
    0
  );
});
</script>

<template>
  <!DOCTYPE html>
  <html lang="es">
    <head>
      <meta charset="UTF-8" />
      <meta http-equiv="X-UA-Compatible" content="IE=edge" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <title>GuitarLA</title>
      <link rel="preconnect" href="https://fonts.googleapis.com" />
      <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
      <link
        href="https://fonts.googleapis.com/css2?family=Outfit:wght@400;700;900&display=swap"
        rel="stylesheet"
      />
      <link rel="stylesheet" href="./src/style.css" />
    </head>
    <header class="py-5 header">
      <div class="container-xl">
        <div class="row justify-content-center justify-content-md-between">
          <div class="col-8 col-md-3">
            <a href="index.html">
              <img class="img-fluid" src="/img/logo.svg" alt="imagen logo" />
            </a>
          </div>
          <nav class="col-md-6 a mt-5 d-flex align-items-start justify-content-end">
            <div class="carrito">
              <img class="img-fluid" src="/img/carrito.png" alt="imagen carrito" />
              <div id="carrito" class="bg-white p-3">
                <p v-if="cart.length === 0" class="text-center m-0">
                  El carrito esta vacio
                </p>
                <div v-else>
                  <table v-if="cart.length > 0" class="w-100 table">
                    <thead>
                      <tr>
                        <th>Imagen</th>
                        <th>Nombre</th>
                        <th>Precio</th>
                        <th>Cantidad</th>
                        <th></th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr v-for="product in cart">
                        <td>
                          <img
                            class="img-fluid"
                            :src="'/img/' + product.img + '.jpg'"
                            :alt="'imagen guitarra' + product.name"
                          />
                        </td>
                        <td>{{ product.name }}</td>
                        <td class="fw-bold">${{ product.price }}</td>
                        <td class="flex align-items-start gap-4">
                          <button
                            type="button"
                            class="btn btn-dark"
                            @click="$emit('decrement-quantity', product.id)"
                          >
                            -
                          </button>
                          {{ product.quantity }}
                          <button
                            type="button"
                            class="btn btn-dark"
                            @click="$emit('increment-quantity', product.id)"
                          >
                            +
                          </button>
                        </td>
                        <td>
                          <button
                            class="btn btn-danger"
                            type="button"
                            @click="$emit('delete-product', product.id)"
                          >
                            X
                          </button>
                        </td>
                      </tr>
                    </tbody>
                  </table>

                  <p class="text-end">
                    Total pagar: <span class="fw-bold">${{ totalPayment }}</span>
                  </p>
                  <button
                    class="btn btn-dark w-100 mt-3 p-2"
                    @click="$emit('remove-all-products')"
                  >
                    Vaciar Carrito
                  </button>
                </div>
              </div>
            </div>
          </nav>
        </div>
        <!--.row-->

        <div class="row mt-5">
          <div class="col-md-6 text-center text-md-start pt-5">
            <h1 class="display-2 fw-bold">Modelo {{ guitar.name }}</h1>
            <p class="mt-5 fs-5 text-white">
              {{ guitar.description }}
            </p>
            <p class="text-primary fs-1 fw-black">$ {{ guitar.price }} USD</p>
            <button
              type="button"
              class="btn fs-4 bg-primary text-white py-2 px-5"
              @click="$emit('add-to-cart', guitar)"
            >
              Agregar al Carrito
            </button>
          </div>
        </div>
      </div>

      <img class="header-guitarra" src="/img/header_guitarra.png" alt="imagen header" />
    </header>
  </html>
</template>
