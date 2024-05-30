<template>
  <div class="about">
    <WelcomeItem>
      <h2>E-mail</h2>

      <input type="text" v-model="inputValue" placeholder="Digite seu Email..." />
    </WelcomeItem>

    <WelcomeItem>
      <h2>Senha</h2>

      <input type="text" v-model="inputValue" placeholder="Digite sua senha..." />
    </WelcomeItem>

    <WelcomeItem>
      <h2>.</h2>
      <button @click="submitInput">Entrar</button>
    </WelcomeItem>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
