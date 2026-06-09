<script setup>

import Score from './Score.vue';

</script>

<template>
    <header class="header">
        <h1 class="header-title">Запомни слово</h1>
        <Score :score="100" class="header-score" />
        
    </header>        
</template>

<style scoped>

.header {
    color: var(--color-header);
    position: fixed;
    z-index: 1000;
    display: flex;
    justify-content:space-between;
    align-items: center;
    padding: 16px 24px;
    background: transparent;
    width: 100%;

}
.header-title { 
    font-family: var(--font);
    text-transform: uppercase;
    font-weight: 700;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: 12%;
    color: #222222;
    margin: 0;
}
.header-title:hover {
    text-decoration: underline;
    text-decoration-color: var(--color-bg-button);
}
</style>