<template>
    <form action="">
        <input type="number" class="form-control" placeholder="Digite um numero">
        <input type="number" class="form-control mt-3" placeholder="Digite outro numero">
        <input type="submit" class="btn btn-primary mt-3">
    </form>

    <div v-show="most">

    </div>
</template>

<script>
export default {
    name: "ComponenteTeste",
    data() {

    }
}
</script>