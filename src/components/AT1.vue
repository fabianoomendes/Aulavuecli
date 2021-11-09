<template>
    <div class="container-md">
        <form class="my-5">
            <div class="mb-3">
                <label for="exampleFormControlInput1" class="form-label">Digite seu nome</label>
                <input type="text" v-model="input_nome" class="form-control" id="exampleFormControlInput1" placeholder="luiza">
            </div>
            <input type="submit" v-on:click="EnviarForm" class="btn btn-primary">
        </form>

        <div v-show="ativo">
            <ul>
                <li v-for="pessoa in pessoas" :key="pessoa">
                    {{ pessoa }}
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: "AT1",
    data(){ 
        return {
            name: "",
            input: "",
            ativo: false,
            pessoas: []
        }
    },
    methods: {
        EnviarForm(e) {
            e.preventDefault()
            this.nome = this.input_nome
            this.input_nome = ''
            this.pessoas.push(this.nome)
            this.ativo = true
        }
    }
}
</script>