<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de jogadores</h2>
    </div>
    <div class="form-inputs">
    <input type="text" placeholder="Nome jogador"/>
    <button>Salvar</button>
    </div>
    <div class="form-inputs">
    <input type="text" placeholder="Nome do time"/>
    <button>Salvar</button>
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
          <tr>
            <td>1</td>
            <td>nome 1</td>
            <td></td>
            <td>???</td>
          </tr>
          <tr>
            <td>2</td>
            <td>nome 2</td>
            <td></td>
            <td>???</td>
          </tr>
          <tr>
            <td>3</td>
            <td>nome 3</td>
            <td></td>
            <td>???</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
<style>
.title{
  text-align: center;
  margin: 2rem 0;
}

.form-inputs{
  display: flex;
  justify-content: center;
  margin: 2rem 0;
}
.form-inputs input{
  width: 50%;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 10px;
}
.form-inputs button{
  padding: 0.5rem;
  width: 20%;
  border: 1px solid rgb(51, 75, 102);
  border-radius: 10px;
  background-color: rgb(0, 81, 128);
  color: white;
  font-weight: bold;
  margin-left: 1%;
}
.list-iten{
  display: flex;
  justify-content: center;
}
table{
  width: 50%;
  border-collapse: collapse;
  margin: 0 auto;
  border: 1px solid black;
  font-size: 1.1rem;
}
table thead{
  background-color: rgb(216, 34, 34);
  color: white;
  
}

table thead th{
  font-weight: bolder;
  }

table tbody tr{
  text-align: center;
}

table tbody tr:nth-child(odd){
  background-color: rgb(243, 177, 177);
}
</style>