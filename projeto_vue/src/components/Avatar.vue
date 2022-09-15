<template>
    <div>
    <img :src="avatar" :alt="descricao">
    <Reutilizacao />
    </div>
</template>

<script>
import Reutilizacao from './Reutilizacao.vue';

export default {
    name: "Avatar",
    components: {
        Reutilizacao
    },
    data() {
        return {
            avatar: "/img/avatar.png",
            descricao: "Thais Quesada"
        };
    },
    components: { Reutilizacao }
}
</script>