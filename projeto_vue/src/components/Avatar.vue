<template>
    <div>
    <img :src="avatar" :alt="descricao">
    <MudarAvatar @mudar-avatar="trocarAvatar" />
    </div>
</template>

<script>
import MudarAvatar from './MudarAvatar.vue';

export default {
    name: 'Avatar',
    components: {
        MudarAvatar
    },
    data() {
        return {
            avatar: "/img/avatar.png",
            descricao: "Thais Quesada"
        };
    },
    methods: {
        trocarAvatar() {
            this.avatar = "/img/avatar2.png"
        }
    }
}
</script>