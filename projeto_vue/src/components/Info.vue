<template>
    <div>
        <p v-if="esta_trabalhando">Estou trabalhando no momento.</p>
        <p v-else>Estou em busca de novas oportunidades.</p>
        <p>Utilizo as seguintes tecnologias para back-end:</p>
            <ul>
                <li v-for="(tecnologia, index) in tecnologias_backend" v-bind:key="index">
                    {{ tecnologia }}
                </li>
            </ul>
        <p>Utilizo as seguintes tecnologias para front-end:</p>
            <ul>
                <li v-for="tecnologia in tecnologias_frontend" :key="tecnologia.id">
                    {{ tecnologia.linguagem }}</li>
            </ul>
        <div>
            <button @click="showEmail">{{ textoBotao }}</button>
        </div>
        <p v-show="mostrar_email">Mande uma mensagem para: {{ email }}</p>
        <!-- o target="_blank" faz com que o link seja aberto em uma outra aba -->
        <p class="teste">Para acessar meu portfólio, <a v-bind:href="meu_link" target="_blank">clique aqui</a></p>
        <Avatar />
    </div>
</template>

<script>
import Avatar from './Avatar.vue';

export default {
    name: 'Info',
    components: {
        Avatar
    },
    props: {
        email: String,
        esta_trabalhando: Boolean
    },
    data() {
        return {
            mostrar_email: false,
            meu_link: 'https://google.com',
            textoBotao: 'Mostrar e-mail',
            // dados vindo como array
            tecnologias_backend: ['C#', '.NET', 'Java'],
            // dados vindo como objeto
            tecnologias_frontend: [
                {id: 1, linguagem: 'JavaScript'},
                {id: 3, linguagem: 'Vue'}
            ]
        }
    },
    methods: {
        showEmail() {
            this.mostrar_email = !this.mostrar_email
            if(!this.mostrar_email) {
                this.textoBotao = 'Mostrar e-mail'
            } else {
                this.textoBotao = 'Esconder e-mail'
            }
        }
    }
}
</script>

<style>
    .paragrafo-pai {
        color: red;
    }
</style>