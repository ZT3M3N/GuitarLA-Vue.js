<script setup>
const props = defineProps({
  guitar: {
    type: Object,
    required: true,
  },
});

defineEmits(["add-to-cart"]);
</script>

<template>
  <div class="col-md-6 col-lg-4 my-4 row align-items-center">
    <div class="col-4">
      <img
        class="img-fluid"
        :src="'/img/' + guitar.img + '.jpg'"
        :alt="'imagen guitarra' + guitar.name"
      />
    </div>
    <div class="col-8">
      <h3 class="text-black fs-4 fw-bold text-uppercase">{{ guitar.name }}</h3>
      <p>{{ guitar.description }}</p>

      <p class="fw-black text-primary fs-3">$ {{ guitar.price }} USD</p>
      <button
        type="button"
        class="btn btn-dark w-100"
        @click="$emit('add-to-cart', guitar)"
      >
        Agregar al Carrito
      </button>
    </div>
  </div>
</template>
