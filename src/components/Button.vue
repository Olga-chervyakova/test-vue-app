<script setup>
</script>

<template>
    <button class="button">
        <div>
            <slot name="icon" />
        </div>
        <slot />
    </button>
</template>

<style scoped>
.button {
    border: none;
    width: 335px;
    height: 68px;
    padding: 16px 10px;
    background: var(--color-bg-button);
    color: var(--color-primary);
    font-family: var(--font);
    border-radius: 100px;
    font-size: 24px;
    font-weight: 400;
    text-align: center;
    justify-content: center;
    gap: 10px;
    
}
</style>