<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      jogadores: [
        { id: "91dcc0ed-b6bb-4979-ab4b-5747ce552e41", nome: "jogador 1", time:"time 1" },
        { id: "7a3deb3c-2367-463d-a380-ac57a163c9cd", nome: "jogador 2", time:"time 2" },
        { id: "4b7d86bc-f5d1-44b3-a476-da3e9ce2d49e", nome: "jogador 3", time:"time 3"},
      ],
      novo_jogador: "" ,
      novo_time: ""
    };
  },
  methods: {
    salvar(){
       if ((this.novo_jogador !== "") && (this.novo_time !== "")){
      const novo_id = uuidv4();
      this.jogadores.push({
        id: novo_id,
        nome: this.novo_jogador,
        time: this.novo_time
      });
      this.novo_time = "", 
      this.novo_jogador = ""
     }
    },
    excluir(jogadores){
      const indice = this.jogadores.indexOf(jogadores);
      this.jogadores.splice(indice, 1);
    }
  },
};
</script>

<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de jogadores</h2>
    </div>
    <div class="form-inputs">
      <input type="text" placeholder="Nome jogador"  v-model="novo_jogador" @keydown.enter="salvar" />
      <input type="text" placeholder="Nome do time"  v-model="novo_time" @keydown.enter="salvar"/>
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-iten">
      <table>
        <thead>
          <tr>
            <th>ID Jogador</th>
            <th>Nome</th>
            <th>idade</th>
            <th>ID Time</th>
          </tr>
        </thead>
       <tbody>
          <tr v-for="jogador in jogadores" :key="jogador.id">
            <td>
              {{ jogador.id }}
            </td>
            <td>
              {{ jogador.nome }}
            </td>
            <td>{{jogador.time}}</td>
            <td>
              <button>Editar</button>
              <button @click="excluir(jogadores)">Excluir</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
<style>
.title {
  text-align: center;
  margin: 2rem 0;
}

h2{
  color: black;
}

.form-inputs {
  display: flex;
  justify-content: center;
  margin: 2rem 0;
}

.form-inputs input {
  width: 30%;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 10px;
}

.form-inputs button {
  padding: 0.5rem;
  width: 20%;
  border: 1px solid rgb(51, 75, 102);
  border-radius: 10px;
  background-color: rgb(0, 81, 128);
  color: white;
  font-weight: bold;
  margin-left: 1%;
}

.list-iten {
  display: flex;
  justify-content: center;
}

table {
  width: 50%;
  border-collapse: collapse;
  margin: 0 auto;
  border: 1px solid black;
  font-size: 1.1rem;
}

table thead {
  background-color: rgb(216, 34, 34);
  color: white;
}

table thead th {
  font-weight: bolder;
}

table tbody tr {
  text-align: center;
}

table tbody tr:nth-child(odd) {
  background-color: rgb(243, 177, 177);
}
</style>