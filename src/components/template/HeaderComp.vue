<template>
  <header>
    <div class="menu-esquerdo">
      <span> <RouterLink to="/">Home</RouterLink> </span>
      <span>|</span>
      <span> <RouterLink to="/editoras">Editoras</RouterLink> </span>
      <span>|</span>
      <span> <RouterLink to="/livros">Livros</RouterLink> </span>
      <span>|</span>
      <span> <RouterLink to="/cartegorias">Cartegorias</RouterLink> </span>
      <span>|</span>
      <span> <RouterLink to="/autores">Autores</RouterLink> </span>
    </div>
    <div class="menu-direito">
      <span> {{ usuario }} </span>
      <span>Sair</span>
    </div>
  </header>
</template>

<style>
header {
  height: 10%;
  background-image: linear-gradient(to right, rgb(189, 115, 18) , rgb(221, 238, 70));
  color: white;
  font-size: 1.3rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-left: 20px;
}
header span {
  padding: 0 20px;
}
</style>
