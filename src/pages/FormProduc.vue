<template>
    <q-page>
        <h4>Productos</h4>
        <q-form 
        class="row q-col-gutter-md"
        @submit.prevent="provesarFormulario"
        @reset="onReset"
        >
            <div class="col-12 col-sm-3">
                <q-input
                type="text"
                label="Name"
                v-model="producto"
                :rules="[ val => val && val.length > 0 || 'Por favor escribe algo']"
                />
            </div>

            <div class="col-12 col-sm-3">
                <q-input
                type="text"
                label="Descripcion"
                v-model="descripcion"
                :rules="[ val => val && val.length > 0 || 'Por favor escribe algo']"
                />
            </div>
            
            <div class="col-12 col-sm-3">
                <q-input
                type="text"
                label="Referencia"
                v-model="referencia"
                :rules="[ val => val && val.length > 0 || 'Por favor escribe algo']"
                />
            </div>

            <div class="col-12 col-sm-3">
                <q-input
                label="Precio"
                v-model="precio"
                type="number"
                :rules="[ val => val && val.length > 0 || 'Por favor escribe algo']"
                />
            </div>
            
            <div class="col-12 text-center">
                <q-btn color="positive" label="Submit" type="submit" />
                <q-btn color="negative" label="Reset" type="reset" class="q-ml-sm" />
            </div>
        </q-form>
    </q-page>
</template>
<script>
import {ref} from 'vue'
import { useQuasar } from 'quasar'
export default {

    setup(){
        const $q = useQuasar()

        const producto = ref(null)
        const descripcion = ref(null)
        const referencia = ref(null)
        const precio = ref(null)

        const productos = ref([])

        const provesarFormulario = () =>{
            $q.notify({
                color: 'green-4',
                textColor: 'white',
                icon: 'cloud_done',
                message: 'Submitted'
            })

            productos.value = [...productos.value, {
                name: producto.value,
                descripcion: descripcion.value,
                referencia: referencia.value,
                precio: precio.value
            }]
        } 

        const onReset = () => {
            producto.value = null
            descripcion.value = null
            variaciones.value = null
        }
        
        return{
            producto,
            descripcion,
            referencia,
            precio,
            provesarFormulario,
            onReset,
            productos
        }
    }
}
</script>