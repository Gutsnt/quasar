<template>
    <q-table
      title="Productos"
      :columns="columns"
      :rows="rows"
      row-key="name"
    >
    </q-table>
  </template>
  
<script>
const columns = [
  {
    name: 'producto',
    required: true,
    label: 'Producto',
    align: 'left',
    field: row => row.name,
    format: val => `${val}`,
    sortable: true
  },
  { 
    name: 'descripcion', 
    align: 'center', 
    label: 'Descripcion', 
    field: 'descripcion', 
    sortable: true
 },
  { 
    name: 'variacion', 
    label: 'Variacion ', 
    field: 'Variacion', 
    sortable: true
 },
  { 
    name: 'referencia', 
    label: 'refencia', 
    field: 'referencia', 
    sortable: true
 },
  { 
    name: 'precio', 
    label: 'Precio', 
    field: 'precio', 
    sortable: true
 },
  
]
const rows = [
  {
    name: 'Producto 1',
    descripcion: 'Descripcions 1',
    Variacion: 'Variacion 1',
  },
  
  {
    name: 'Producto 1',
    descripcion: 'Categoria 1',
    Variacion: 'Variacion 1',
  },
  
  
]

export default {
  named: 'ListProduc', // Nombre del componente
    setup(){
        return {
        columns,
        rows
        }
    },
  // Otras opciones de configuración del componente
}


</script>
  