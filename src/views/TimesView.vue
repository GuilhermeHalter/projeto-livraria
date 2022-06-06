<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de times</h2>
    </div>
    <div class="form-input">
    <input type="text" />
    <button>Salvar</button>
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
          <tr>
            <td>1</td>
            <td>Time 1</td>
            <td>???</td>
          </tr>
          <tr>
            <td>2</td>
            <td>Time 2</td>
            <td>???</td>
          </tr>
          <tr>
            <td>3</td>
            <td>Time 3</td>
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

.form-input{
  display: flex;
  justify-content: center;
  margin: 2rem 0;
}
.form-input input{
  width: 50%;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 10px;
}
.form-input button{
  padding: 0.5rem;
  width: 20%;
  border: 1px solid rgb(53, 102, 51);
  border-radius: 10px;
  background-color: green;
  color: white;
  font-weight: bold;
  margin-left: 1%;
}
.list-itens{
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
  background-color: rgb(56, 216, 34);
  color: white;
  
}

table thead th{
  font-weight: bolder;
  }

table tbody tr{
  text-align: center;
}

table tbody tr:nth-child(odd){
  background-color: rgb(177, 243, 177);
}
</style>