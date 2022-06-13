<script>
import { v4 as uuidv4 } from "uuid";

export default {
  data() {
    return {
      times: [
        { id: "6f271bf7-1fbe-4f3c-a469-8fb458817622", nome: "time 1" },
        { id: "3532f30f-113d-47d8-8cea-87f27f9e6902", nome: "time 2" },
        { id: "64b74601-7900-44fb-a07b-43dab9361e0c", nome: "time 3" },
        { id: "5e3167b9-047e-4b58-8be6-422957cfbec3", nome: "time 4" }
      ],
      novo_time: ""
    };
  },
  methods: {
    salvar(){
      const novo_id = uuidv4();
      this.times.push({
        id: novo_id,
        nome: this.novo_time,
      })
    },
  },
};
</script>

<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de times</h2>
    </div>
    <div class="form-input">
      <input type="text" v-model="novo_time" />
      <button @click = "salvar">Salvar</button>
    </div>
    <div class="list-">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Nome</th>
            <th>Ações</th>
          </tr>
        </thead>
         <tbody>
          <tr v-for="time in times" :key="time.id">
            <td>
              {{ time.id }}
            </td>
            <td>
              {{ time.nome }}
            </td>
            <td>????</td>
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

.form-input {
  display: flex;
  justify-content: center;
  margin: 2rem 0;
}

.form-input input {
  width: 50%;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 10px;
}

.form-input button {
  padding: 0.5rem;
  width: 20%;
  border: 1px solid rgb(53, 102, 51);
  border-radius: 10px;
  background-color: green;
  color: white;
  font-weight: bold;
  margin-left: 1%;
}

.list-itens {
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
  background-color: rgb(56, 216, 34);
  color: white;

}

table thead th {
  font-weight: bolder;
}

table tbody tr {
  text-align: center;
  color: black;
}

table tbody tr:nth-child(odd) {
  background-color: rgb(177, 243, 177);
}
</style>