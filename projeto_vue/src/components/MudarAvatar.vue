<template>
    <div>
    <button @click="$emit('mudarAvatar')">Trocar sua imagem de perfil</button>
    </div>
</template>

<script>
    export default {
        name: 'MudarAvatar',
        emits: ['mudarAvatar']
    }
</script>
