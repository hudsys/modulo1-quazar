<template>
  <q-page class="container flex column justify-around flex-center justify-around">
  <q-img
      src="../assets/Vetor-Logo-Cor.jpeg"
      spinner-color="white"
      style="height: auto; max-width: 230px"
   />

   <H5 class="title q-ma-sm text-center">{{ frases[index] }}</H5>

   <div class="flex justify-around full-width">
    <q-btn 
      class="button"
      @click="randomPosition" 
      rounded 
      label="skip"
    />   
    <q-btn 
      class="button"
      @click="randomPosition" 
      rounded 
      label="Gerar"
    />   
   </div>
  </q-page>
</template>

<script>
export default {
  name: 'FraseDoDia',
  data() {
    return  { frases: [
      'Frase 1',
      'Frase 2',
      'Frase 3',
      'Frase 4',
      'Frase 5'
    ],
    index: 0,
   };
  },
   methods: {
    randomPosition(){
      let index = parseInt(Math.random() * 5 + 0);
      this.index = index;
   },
  },
  created(){
    this.randomPosition();
  }
}
</script>

<style lang="stylus" scoped>
  .container { 
    background-color: #f95179;
  }
  .title {
    color: #fff;
  }
  .button {
    color: #fff;
    height: 60px;
    background-color: #262525;
  }

</style>