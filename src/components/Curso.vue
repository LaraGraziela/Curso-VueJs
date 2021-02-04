<template>
  <div class="hello">
    <h1>Olá {{name}}!</h1>
    <input type="text" v-model="name"><br><br>
    
    <a :href="link">Acesse o meu GIT!</a>
  </div>
</template>

<script>
export default {
  data: () => ({
    name: 'Lara',
    link: 'https://github.com/LaraGraziela/PDI-Track',
    decoration: 'underline'
  })
}
</script>

<style>

</style>
