<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'
const data = ref([])
const fetchData = async () => {
  try {
    const response = await axios.get('https://dolarapi.com/v1/dolares')
    data.value = response.data
  } catch (error) {
    console.error('Error al obtener los datos:', error)
  }
}
onMounted(() => {
  fetchData()
})
</script>

<template>
    <div v-if="data.length > 0">
    <h1 class="oficial">Dólar Oficial</h1>  
    <p class="dolaroficial">
      Compra: {{ data[0].compra }} <br>
      Venta: {{ data[0].venta }}
    </p>
    <h1 class="blue">Dólar Blue</h1>
    <p class="dolarblue">
      Compra: {{ data[1].compra }} <br>
      Venta: {{ data[1].venta }}
    </p>

    <h1 class="bolsa">Dólar Bolsa</h1>
    <p class="dolarbolsa">
      Compra: {{ data[2].compra }} <br>
      Venta: {{ data[2].venta }}
    </p>
    <h1 class="ccl">Dólar CCL</h1>
    <p class="dolarccl">
      Compra: {{ data[3].compra }} <br>
      Venta: {{ data[3].venta }}
    </p>
    
    <h1 class="mayorista">Dólar Mayorista</h1>
    <p class="dolarmayorista">
      Compra: {{ data[4].compra }} <br>
      Venta: {{ data[4].venta }}
    </p>
    <h1 class="cripto">Dólar Cripto</h1>
    <p class="dolarcripto">
      Compra: {{ data[5].compra }} <br>
      Venta: {{ data[5].venta }}
    </p>

    <h1 class="tarjeta">Dólar Tarjeta</h1>
    <p class="dolartarjeta">
      Compra: {{ data[6].compra }} <br>
      Venta: {{ data[6].venta }}
    </p>

  </div>

  <div v-else>
    <p>Cargando datos...</p>
  </div>
</template>

<style scoped>
</style>
