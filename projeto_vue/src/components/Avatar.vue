<template>
    <img :src="avatar" :alt="descricao">
</template>

<script>
export default {
    name: 'Avatar',
    data() {
        return {
            avatar: '/img/avatar.png',
            descricao: 'Thais Quesada'
        }
    }
}
</script>