<script setup>
  //ejercicio 1
  var vectorNombre = ["Franco", "Alexis", "Julian", "Enzo"]

  //ejercicio 2
  var dicNombre = [{nombre: "Franco", apellido: "Ortiz", curso: "6a"}, 
                  {nombre: "Alexis", apellido: "olmos", curso: "2a"}, 
                  {nombre: "Julian", apellido: "Ortiz", curso: "6a"}, 
                  {nombre: "Enzo", apellido: "Ortiz", curso: "6a"}]

  //ejercicio 3
  import { ref } from 'vue'
  var codigo = ref("");
  var articulo = ref("");
  var precio = ref("");
  var cantidad = ref("");

  //ejercicio 4
  var numero1 = ref("");
  var numero2 = ref("");
  var operacion = ref("");

</script>

<template>
  
  <div class = "ejercicio1">
    <h1>ejercicio 1</h1>
    <table>
      <tr>
        <th>Nombre</th>
      </tr>
      <tr v-for="nombre in vectorNombre">
        <td>{{ nombre }}</td>
      </tr>
    </table>
  </div>

    <h1>ejercicio 2</h1>
    <table>
      <tr>
        <th>Nombre</th>
        <th>Apellido</th>
        <th>Curso</th>
      </tr>
      <tr v-for="persona in dicNombre">
        <td>{{ persona.nombre }}</td>
        <td>{{ persona.apellido }}</td>
        <td>{{ persona.curso }}</td>
      </tr>
    </table>

    <h1>ejercicio 3</h1>
    <form>
      <label for="codigo">Codigo</label>
      <input type="text" id="codigo" v-model="codigo">
      <label for="articulo">Articulo</label>
      <input type="text" id="articulo" v-model="articulo">
      <label for="precio">Precio</label>
      <input type="text" id="precio" v-model="precio">
      <label for="cantidad">Cantidad</label>
      <input type="text" id="cantidad" v-model="cantidad">
    </form>

    <table>
      <tr>
        <th>Codigo</th>
        <th>Articulo</th>
        <th>Precio</th>
        <th>Cantidad</th>
      </tr>
      <tr>
        <td>{{ codigo }}</td>
        <td>{{ articulo }}</td>
        <td>{{ precio }}</td>
        <td>{{ cantidad }}</td>
      </tr>
    </table>

    <h1>ejercicio 4</h1>
    <form>
      <label for="numero1">Numero 1</label>
      <input type="text" id="numero1" v-model="numero1">
      <label for="numero2">Numero 2</label>
      <input type="text" id="numero2" v-model="numero2">
      <label for="operacion">Operacion</label>
      <select id="operacion" v-model="operacion">
        <option value="+">Suma</option>
        <option value="-">Resta</option>
        <option value="*">Multiplicacion</option>
        <option value="/">Division</option>
      </select>
    </form>

    <h2 v-if="operacion == '+'">El resultado es: {{ parseInt(numero1) + parseInt(numero2) }}</h2>
    <h2 v-else-if="operacion == '-'">El resultado es: {{ parseInt(numero1) - parseInt(numero2) }}</h2>
    <h2 v-else-if="operacion == '*'" >El resultado es: {{ parseInt(numero1) * parseInt(numero2) }}</h2>
    <h2 v-else-if="operacion == '/'">El resultado es: {{ parseInt(numero1) / parseInt(numero2) }}</h2>

</template>

<style scoped>
  .ejercicio1 {
    background-color: blue;
    }
</style>