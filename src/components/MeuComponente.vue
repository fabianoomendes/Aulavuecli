<template>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Mochiy+Pop+One&display=swap" rel="stylesheet">
  <div class="container-lg">
    <div class="row">
      <div class="col col-md-9">
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
              <div class="quantidade" :class="{esconder :!produto.ativo}">
                <button @click.stop="produto.count--" :disabled="produto.count <= 1 || produto.qtd == 0" class="btn btn-primary btn-sm">-</button>
                <span class="mx-2">{{ produto.count }}</span>
                <button @click.stop="produto.count++" :disabled="produto.qtd == 0" class="btn btn-primary btn-sm">+</button>
              </div>
            </div>
          </div>
        </section>
      </div>

      <div class="col col-md-3" v-show="total() > 0">
        <strong>Resumo do pedido</strong>
        <table class="table table-striped">
          <thead>
            <tr>
              <th>Qtd</th>
              <th>Item</th>
              <th>Total</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="produto in produtos" :key="produto.nome">
              <td v-if="produto.ativo">{{ produto.count}}</td>
              <td v-if="produto.ativo">{{ produto.nome }}</td>
              <td v-if="produto.ativo">{{ (produto.count * produto.valor).toFixed(2).toString().replace('.', ',') }}</td>
            </tr>
          </tbody>
          <tfoot>
            <tr>
              <th></th>
              <th>Total</th>
              <th>{{ total().toFixed(2).toString().replace('.', ',') }}</th>
            </tr>
          </tfoot>
        </table>
      </div>
    </div>
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
          "qtd": 0,
          "count": 1
        },
        {
          "foto": "assets/image2.jpg",
          "nome": "Kit Inoar",
          "valor": 15.00,
          "ativo": false,
          "qtd": 10,
          "count": 1
        },
        {
          "foto": "assets/image3.jpg",
          "nome": "Olive Oil",
          "valor": 23.54,
          "ativo": false,
          "qtd": 0,
          "count": 1
        },
        {
          "foto": "assets/image4.jpg",
          "nome": "Repos",
          "valor": 30.00,
          "ativo": false,
          "qtd": 10,
          "count": 1
        },
        {
          "foto": "assets/image5.png",
          "nome": "Cachos",
          "valor": 30.00,
          "ativo": false,
          "qtd": 5,
          "count": 1
        },
        {
          "foto": "assets/image6.jpg",
          "nome": "Mealiza",
          "valor": 30.00,
          "ativo": false,
          "qtd": 50,
          "count": 1
        },
        {
          "foto": "assets/image7.jpg",
          "nome": "Mealiza",
          "valor": 30.00,
          "ativo": false,
          "qtd": 0,
          "count": 1
        },
        {
          "foto": "assets/image8.png",
          "nome": "Mealiza",
          "valor": 30.00,
          "ativo": false,
          "qtd": 100,
          "count": 1
        }
      ]
    }
  },
  methods: {
    total() {
      let total = 0
      this.produtos.forEach(function(item) {
        if(item.ativo){
          total += item.valor * item.count
        }
      })
      return total
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
    position: relative;
    flex-basis: 20%;
    min-width: 200px;
    box-shadow: 5px 5px 10px 5px rgba(0, 0, 0, 0.226);
    padding-bottom: 10px;
  }
  .prodIndis{
    padding-left: 6px;
    color: #FFF;
    background: rgb(109, 109, 109);
  }

  .esconder{
    visibility: hidden;
  }
  .quantidade{
    position: absolute;
    bottom: 10px;
  }
</style>