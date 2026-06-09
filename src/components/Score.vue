<script setup>
import IconSmall from '../icons/IconSmall.vue';

const props = defineProps ({
    score: {
        type: [Number, String],
        required: false,
        default: 0
    }
});
</script>

<template>
    <div class="score-container">
        <span class="score-value">{{ props.score }}</span>
        <IconSmall class="score-icon" />
    </div>
</template>
<style scoped>

.score-container {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    width: fit-content;
    padding: 12px 16px;
    border-radius: 24px;
    box-sizing: border-box;
    overflow: visible;
    background-color: #CCE8FF;
    width: 110px;
    margin-right: 60px;
}
.score-icon {
    width: 24px;
    height: 24px;
}
.score-value {
    font-family: var(--font);
    font-weight: 700;
    font-size: 16px;
    line-height: 24px;
    margin-left: 8px;
    color: var(--color-bg-button);
    text-align: center;
    white-space: nowrap;
}
</style>