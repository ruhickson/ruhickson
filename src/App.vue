<script setup>
import { ref } from 'vue'
import Header from './layouts/Header.vue';
import Main from './layouts/Main.vue';
import Footer from './layouts/Footer.vue';
import QualificationsSidebar from './components/QualificationsSidebar.vue'

const showQualifications = ref(false)
</script>

<template>
    <Header @open-qualifications="showQualifications = true" />
    <QualificationsSidebar :isOpen="showQualifications" @close="showQualifications = false" />
    <Main/>
    <Footer />
</template>

<style scoped></style>
