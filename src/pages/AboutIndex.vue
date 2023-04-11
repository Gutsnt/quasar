<template>
    <pre>{{ product }}</pre>
    <ListProduc></ListProduc>
</template>

<script>
import ListProduc from 'src/components/ListProduc.vue';
import {ref} from 'vue'
  

export default {
    
    
    named: "ListProduc",
    components: { ListProduc },
    
    setup(){
        
        const product = ([])

        const obtenerProductos = async () => {
            try {
                fetch('http://127.0.0.1:8000/api/productos')
                .then(response => response.json())
                .then(data => {
                console.log(data.productos);
                product.value = data.productos
                })
                .catch(error => {
                console.error('Error al obtener productos:', error);
                });
            } catch (error) {
                
            }
        }
        
        return{
            product
        }
        
    }
}
</script>
