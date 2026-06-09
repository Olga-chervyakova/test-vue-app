<script setup>
import Button from "./components/Button.vue";
import Header from "./components/Header.vue";
import Card from "./components/Card.vue";

const handleCardFlip = (isFlipped) => {
  // eslint-disable-next-line no-undef
  console.log('Карточка перевернулась:', isFlipped);
};

const handleStatusChange = (status) => {
  // eslint-disable-next-line no-undef
  console.log('Статус изменён:', status);
};
</script>

<template>
  <div id="app">
    <Header />
  <main class="main">
    <Button>Начать игру</Button>
    <Card
        english-word="Hello"
        russian-word="Привет"
        @flip="handleCardFlip"
        @status-change="handleStatusChange"
      />
  </main> 
  </div> 
</template>

<style scoped>
.main {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 20px;
}


</style>
