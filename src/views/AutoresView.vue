<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      autores: [
        {
          id_autor: "4b95ec3f-c3a0-49d9-971d-b3696657fbbd",
          nome: "Mauricio de souza",
        },
        {
          id_autor: "ec38e964-9ddc-4d39-b6e3-688e239f8da9",
          nome: "Araki Hirohiko",
        },
        {
          id_autor: "d48aca58-0c61-46fc-896f-9ea630a90cfb",
          nome: "Jojo Moyes",
        },
      ],
      novo_autor: {
        nome: "",
      },
      indice_editar: -1,
    };
  },
  methods: {
    salvar() {
      if (this.novo_autor.nome !== "") {
        if (this.novo_autor.id_autor) {
          this.autores.splice(this.indice_editar, 1, this.novo_autor);
          this.indice_editar = -1;
        } else {
          this.novo_autor.id_autor = uuidv4();
          this.autores.push(this.novo_autor);
        }
        this.novo_autor = {
          descricao: "",
        };
      }
    },
    excluir(autor) {
      const indice = this.autores.indexOf(autor);
      this.autores.splice(indice, 1);
    },
    editar(autor) {
      const indice = this.autores.indexOf(autor);
      this.indice_editar = indice;
      Object.assign(this.novo_autor, autor);
    },
  },
};
</script>
<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de autores</h2>
    </div>
    <div class="form-input">
      <input
        @keyup.enter="salvar"
        v-model="novo_autor.nome"
        type="text"
        placeholder="Nome do autor"
        class="input-maior"
      />

      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-editoras">
      <table>
        <thead>
          <tr>
            <th>ID-autor</th>
            <th>Descrição</th>
            <th>Ações</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="autor in autores" :key="autor.id">
            <td>
              {{ autor.id_autor }}
            </td>
            <td>
              {{ autor.nome }}
            </td>
            <td>
              <button @click="editar(autor)">Editar</button>
              <button @click="excluir(autor)">Excluir</button>
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
.form-input {
  display: flex;
  justify-content: center;
  margin: 2rem 0;
}
.input-maior {
  width: 30%;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 10px;
}
.form-input button {
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
  width: 80%;
  border-collapse: collapse;
  margin: 0 auto;
  border: 1px solid black;
  font-size: 1.1rem;
}
table thead {
  background-color: rgb(196, 135, 4);
  color: rgb(255, 255, 255);
}
table thead th {
  font-weight: bolder;
}
table tbody tr {
  text-align: center;
}
table tbody tr:nth-child(odd) {
  background-color: rgb(241, 219, 21);
}
table tbody td{
  color:black
}
</style>