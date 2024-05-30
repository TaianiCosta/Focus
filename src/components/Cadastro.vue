<script setup lang="ts">
import WelcomeItem from './WelcomeItem.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'
</script>

<template>
  <WelcomeItem>
    <template #icon>
      <DocumentationIcon />
    </template>
    <template #heading>Nome da Loja</template>

    <input type="text" v-model="inputValue" placeholder="Digite nome da Loja..." />
    <button @click="submitInput">Verificar</button>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <ToolingIcon />
    </template>
    <template #heading>E-mail</template>

    <input type="text" v-model="inputValue" placeholder="Digite seu Email..." />
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <EcosystemIcon />
    </template>
    <template #heading>Senha</template>

    <input type="text" v-model="inputValue" placeholder="Digite sua senha..." />
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <CommunityIcon />
    </template>
    <template #heading>Confirmação de Senha</template>

    <input type="text" v-model="inputValue" placeholder="Digite sua senha novamente..." />
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <SupportIcon />
    </template>
    <template #heading></template>

    <button @click="submitInput">Criar minha conta Grátis</button>
  </WelcomeItem>
</template>
