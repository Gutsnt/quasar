<template>
    <q-page>
      <q-container class="q-pt-xl">
        <h1 class="text-h3">Productos y Variaciones</h1>
        <q-list bordered>
          <q-item
            v-for="producto in productos"
            :key="producto.id"
            clickable
            @click="showVariaciones(producto)"
          >
            <q-item-section>
              <h2 class="text-h5">{{ producto.name }}</h2>
              <q-item-label>{{ producto.descripcion }}</q-item-label>
            </q-item-section>
            <q-item-section side>
              <q-item-label>
                {{ producto.variaciones.length }} Variaciones
              </q-item-label>
            </q-item-section>
          </q-item>
        </q-list>
      </q-container>
    </q-page>
  </template>
  
  <script>
  export default {
    data() {
      return {
        productos: [],
      };
    },
    mounted() {
      this.fetchProductos();
    },
    methods: {
      fetchProductos() {
        // Hacer la solicitud GET a la API de productos y variaciones
        // utilizando la librería Axios o la que prefieras
        // y asignar la respuesta a la variable "productos"
        axios
          .get('/api/productos')
          .then(response => {
            this.productos = response.data;
          })
          .catch(error => {
            console.error(error);
          });
      },
      showVariaciones(producto) {
        // Mostrar las variaciones del producto seleccionado
        // utilizando la lógica que desees, por ejemplo, navegando
        // a una nueva ruta o mostrando un diálogo modal
        console.log('Mostrar variaciones de producto:', producto);
      },
    },
  };
  </script>
  