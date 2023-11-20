<template>
    <div>
      <h1>Listado de Carreras</h1>
      <ul>
        <li v-for="carrera in carreras" :key="carrera.id">
          {{ carrera.nombre }}
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  
  import axios from 'axios';
  
  export default {
    data() {
      return {
        carreras: [],
      };
    },
    mounted() {
      axios
        .get('http://127.0.0.1:8000/api/carreras')
        .then(response => (this.carreras = response.data))
        .catch(error => {
          console.error('Error al cargar las carreras:', error);
        });
    },
  };
  </script>
  
  <style>
  </style>
  