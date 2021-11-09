<template>
    <div class="container-md">
        <div class="calculadora">
            <div class="tela">
                <input type="text">
            </div>
            <div>
                
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Calculadora',
    data() {
        return {

        }
    }
}
</script>

<style>
.container-md {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.calculadora {
    background: rgba(28, 28, 28, 0.548);
    width: 400px;
    height: 500px;
    border-radius: 24px;
    padding: 10px;
}

.tela > input{
    width: 100%;
    height: 80px;
    border-top-left-radius: 24px;
    border-top-right-radius: 24px;
    border: none;
    font-size: 35px;
    font-weight: bold;
}

</style>