<template>
    <div>
        <p v-if="esta_trabalhando">Estou trabalhando no momento.</p>
        <p v-else>Estou em busca de novas oportunidades.</p>
        <p>Utilizo as seguintes tecnologias:</p>
            <ul>
                <li>JavaScript</li>
                <li>C#</li>
                <li>Java</li>
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
    data() {
        return {
            esta_trabalhando: true,
            mostrar_email: false,
            email: 'contato@email.com',
            meu_link: 'https://google.com',
            textoBotao: 'Mostrar e-mail'
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