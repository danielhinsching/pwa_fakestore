<script setup>
import { ref } from 'vue';
import { useScreen } from '@/composables/screen';
const barraInferior = ref(isMobile)
const { isMobile } = useScreen();
</script>
<template>
    <footer>
        <barraInferior/>
    </footer>
</template>