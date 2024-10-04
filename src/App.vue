<template>
  <div class="form-wrapper mt-4 mx-5">
    <form>
      <div>
        <label>Título de la tarjeta: </label>
        <input class="form-control" v-model="usuario.titulo"/>
      </div>

      <div>
        <label>Chip SRC: </label>
        <input class="form-control" v-model="usuario.chip" placeholder="/chip.png"/>
      </div>

      <div>
        <label>Número: </label>
        <input class="form-control" v-model="usuario.numero"/>
      </div>

      <div>
        <label>Fecha de expiración: </label>
        <input class="form-control" v-model="usuario.fecha"/>
      </div>

      <div>
        <label>Propietario: </label>
        <input class="form-control" v-model="usuario.nombre"/>
      </div>

      <div>
        <label>Tipo de tarjeta SRC: </label>
        <input class="form-control" v-model="usuario.visa" placeholder="/visa.png"/>
      </div>
    </form>

    <div class="carnet">
      <h3>{{ usuario.titulo }}</h3>
      <img width="40" :src="usuario.chip" alt="" />
      <div>
        <h2>{{ usuario.numero }}</h2>
        <span>Fecha Exp: <b>{{ usuario.fecha }}</b></span>
      </div>
      <footer>
        <span>{{ usuario.nombre }}</span>
        <img :src="usuario.visa" width="60" />
      </footer>
    </div>

  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      usuario: {
        titulo: "",
        numero: "",
        fecha: "",
        nombre: "",
        chip: "",
        visa: ""
      },
      continentes: ["Asia", "Europa", "África", "América", "Oceanía"], 
    };
  },
};
</script>

<style>
      * {
        margin: 0;
      }
      body {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 60vh;
        font-size: 10px;
        font-family: sans-serif;
      }

      #app {
        display: flex;
        gap: 40px;
      }
      form {
        padding: 18px;
        border-radius: 20px;
        border: ridge 1px;
        box-shadow: 1px 1px 1px 1px gray;
        font-weight: bold;
        display: flex;
        flex-direction: column;
        gap: 15px;
        justify-content: center;
      }
      form div {
        display: grid;
        grid-template-columns: 100px 200px;
        align-items: center;
        gap: 5px;
      }

      form div label {
        text-align: right;
      }

      .carnet {
        width: 400px;
        height: 230px;
        background: #1c1a1e;
        color: white;
        border-radius: 20px;
        padding: 20px;
        box-shadow: 0px 0px 10px 2px black;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
      }

      h3 {
        font-size: 20px;
      }

      h2 {
        font-size: 30px;
        letter-spacing: 10px;
        margin-bottom: 15px;
        text-shadow: 0px 0px 1px gold;
        font-family: Times;
      }

      b {
        font-size: 16px;
      }

      footer {
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
        font-weight: bold;
        font-size: 18px;
        text-transform: uppercase;
        font-style: italic;
      }
    </style>