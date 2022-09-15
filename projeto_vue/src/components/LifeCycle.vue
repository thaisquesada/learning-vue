<template>
    <h1>Meu nome é: {{ nome }}</h1>
</template>

<script>
export default {
    naame: 'LifeCycle',
    data() {
        return {
            nome: 'ainda não sei'
        }
    },
    created() {
        setTimeout(() => {
            this.nome = 'Thais'
        }, 1000)
    },
    mounted() {
        setTimeout(() => {
            this.nome = 'Quesada'
        }, 2000);

        this.lifeCycle()
    },
    methods: {
        lifeCycle() {
            console.log("Executou!")
        }
    }
}
</script>
