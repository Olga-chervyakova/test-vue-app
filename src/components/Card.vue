<script setup>
import { ref } from 'vue';

const props = defineProps({
  englishWord: {
    type: String,
    required: true
  },
  russianWord: {
    type: String,
    required: true
  }
});

const isFlipped = ref(false);
const status = ref(null);

const emit = defineEmits(['flip', 'status-change']);

const handleFlip = () => {
  isFlipped.value = !isFlipped.value;
  emit('flip', isFlipped.value); 
};

const handleCorrect = () => {
  status.value = 'correct';
  emit('status-change', 'correct');
};

const handleIncorrect = () => {
  status.value = 'incorrect';
  emit('status-change', 'incorrect');
};
</script>

<template>
  <div
    class="card"
    :class="{ 'flipped': isFlipped, 'correct': status === 'correct', 'incorrect': status === 'incorrect' }"
    @click="handleFlip"
  >
    <div class="card-inner">
      
      <div class="card-number">01</div>
      <div class="card-front">
        <div class="word">{{ props.englishWord }}</div>
      </div>

      
      <div class="card-back">
        <div class="word">{{ props.russianWord }}</div>
        <div class="status-buttons">
          <button
            class="status-btn correct-btn"
            @click.stop="handleCorrect"
          >
            ✅
          </button>
          <button
            class="status-btn incorrect-btn"
            @click.stop="handleIncorrect"
          >
            ❌
          </button>
        </div>
        <div class="flip-text">Перевернуть</div>
      </div>
    </div>
  </div>
</template>
<style scoped>
.card {
    width: 250px;
    height: 376px;
    position: absolute;
    opacity: 1;
    top: 170px;
    left: 66px;
    border-radius: 16px;
    box-shadow: 0px 0px 16px 0px rgba(0, 0, 0, 0.1);
    background: var(--color-primary);
}
.card-inner {
    width: 212px;
    height: 320px;
    position: absolute;
    border: 1px solid #CCE8FF;
    border-radius: 12px;
    top: 28px;
    left: 19px;
    background: var(--color-primary);
    transition: transform 0.6s;
    transform-style: preserve-3d;
}
.card-front, .card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
  box-sizing: border-box;

}
card-front {
  transform: rotateY(0deg);
  background: var(--color-primary);
}

.card-back {
  transform: rotateY(180deg);
  background: var(--color-primary);
}

.card.flipped .card-inner {
  transform: rotateY(180deg);
}

.card-number {
  width: 16px;
  height: 16px;
  position: absolute;
  top: 20px;
  left: 35px;
  font-family: var(--font);
  font-weight: 700;
  font-size: 12px;
  color: #666;
  z-index: 10;
}

.english-word,
.russian-word {
  font-family: 'Roboto', sans-serif;
  font-weight: 400;
  font-size: 18px;
  line-height: 100%;
  letter-spacing: 0;
  text-align: center;
  color: #000000;
  margin: 0 auto;
}

.flip-text {
  width: 89px;
  height: 18px;
  position: absolute;
  top: 339px;
  left: 80px;
  display: flex;
  gap: 10px;
  opacity: 1;
  padding-right: 4px;
  padding-left: 4px;
  background: #222222;
  font-family: 'Roboto', sans-serif;
  font-weight: 700;
  font-size: 12px;
  line-height: 18px;
  letter-spacing: 0.12em;
  color: white;
  justify-content: center;
  align-items: center;
}

.status-buttons {
  width: 97px;
  height: 18px;
  position: absolute;
  top: 316px;
  left: 105px;
  display: flex;
  gap: 10px;
  opacity: 1;
}

.status-btn {
  width: 40px;
  height: 40px;
  border: none;
  border-radius: 50%;
  font-family: 'Roboto', sans-serif;
  font-weight: 700;
  font-size: 12px;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
}

.correct-btn {
  background: #C4C4C4;
  color: white;
}

.incorrect-btn {
  background: #C4C4C4;
  color: white;
}

.gray-circle {
  width: 40px;
  height: 40px;
  position: absolute;
  top: 316px;
  left: 105px;
  background: #C4C4C4;
  border-radius: 50%;
}

</style>