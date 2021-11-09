<template>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Mochiy+Pop+One&display=swap" rel="stylesheet">
  <div class="container-md">
    <h4 class="mt-4">Selecione os produtos</h4>
    <section class="itens">
      <div class="card m-3 pt-1" style="width: 18rem;" v-for="produto in produtos" :key="produto.nome" :class="{ativo :produto.ativo}" @click="produto.ativo = !produto.ativo">
        <img class="card-img-top img" :src="produto.foto" alt="Card image cap">
        <div class="prodIndis" v-if="produto.qtd < 1">
          <span>Produto indisponível</span>
        </div>
        <div class="card-body">
          <h5 class="card-title" style="font-weight: bold">{{ produto.nome }}</h5>
          <p class="card-text">R$ {{ produto.valor }}</p>
          <button class="btn btn-primary btn-sm">-</button>
          <span class="mx-2">1</span>
          <button class="btn btn-primary btn-sm">+</button>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'MeuComponente',
  data() {
    return {
      produtos: [
        {
          "foto": "assets/image1.jpg",
          "nome": "Desmaia Cabelo",
          "valor": 10.00,
          "ativo": false,
          "qtd": 0
        },
        {
          "foto": "assets/image2.jpg",
          "nome": "Kit Inoar",
          "valor": 15.00,
          "ativo": false,
          "qtd": 10
        },
        {
          "foto": "assets/image3.jpg",
          "nome": "Olive Oil",
          "valor": 23.54,
          "ativo": false,
          "qtd": 0
        },
        {
          "foto": "assets/image4.jpg",
          "nome": "Repos",
          "valor": 30.00,
          "ativo": false,
          "qtd": 10
        },
        {
          "foto": "assets/image5.png",
          "nome": "Cachos",
          "valor": 30.00,
          "ativo": false,
          "qtd": 5
        },
        {
          "foto": "assets/image6.jpg",
          "nome": "Mealiza",
          "valor": 30.00,
          "ativo": false,
          "qtd": 50
        },
        {
          "foto": "assets/image7.jpg",
          "nome": "Mealiza",
          "valor": 30.00,
          "ativo": false,
          "qtd": 0
        },
        {
          "foto": "assets/image8.png",
          "nome": "Mealiza",
          "valor": 30.00,
          "ativo": false,
          "qtd": 100
        }
      ]
    }
  }
}

</script>


<style scoped>
  .container-md {
    height: 100%;
    /* background: blue; */
  }
  .container-md > h4 {
    text-align: left;
    font-size: 30px;
    font-family: 'Mochiy Pop One', sans-serif;
  }
  .ativo {
    border-color: red;
  }
  .itens {
    /* background: red; */
    width: 100%;
    display: flex;
    flex-wrap: wrap;
  }
  .card {
    flex-basis: 20%;
  }
  .prodIndis{
    padding-left: 6px;
    color: #FFF;
    background: rgb(109, 109, 109);
  }
</style>