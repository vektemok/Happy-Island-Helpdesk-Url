<template>
  <div class="support-page">
    <h1 class="title">Служба поддержки Happy Island</h1>

    <p class="description">
      Если у вас возникли вопросы или нужна помощь — напишите нам.
    </p>

    <ul class="contact-list">
      <li>
        💬 Telegram: 
        <a href="https://t.me/chernyshov_egor" target="_blank">
          @chernyshov_egor
        </a>
      </li>
      <li>
        📧 Email: 
        <a href="mailto:support@happyisland.app">
          support@happyisland.app
        </a>
      </li>
    </ul>

    <form @submit.prevent="handleSubmit" class="feedback-form">
      <label for="message">Ваш вопрос или сообщение:</label>
      <textarea
        id="message"
        v-model="message"
        placeholder="Напишите здесь..."
        required
      ></textarea>
      <button type="submit">Отправить</button>
    </form>

    <p v-if="submitted" class="confirmation">Спасибо! Мы свяжемся с вами в ближайшее время.</p>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const message = ref('')
const submitted = ref(false)

const handleSubmit = () => {
  // Здесь будет логика отправки сообщения (например, API-запрос)
  console.log('Сообщение отправлено:', message.value)
  submitted.value = true
  message.value = ''
}
</script>

<style scoped>
.support-page {
  max-width: 600px;
  margin: auto;
  padding: 2rem;
  font-family: sans-serif;
}

.title {
  font-size: 1.8rem;
  margin-bottom: 0.5rem;
}

.description {
  margin-bottom: 1.5rem;
}

.contact-list {
  list-style: none;
  padding: 0;
  margin-bottom: 2rem;
}

.contact-list li {
  margin-bottom: 0.5rem;
}

.feedback-form {
  display: flex;
  flex-direction: column;
}

textarea {
  min-height: 100px;
  padding: 0.5rem;
  margin-bottom: 1rem;
  font-size: 1rem;
  resize: vertical;
}

button {
  align-self: flex-start;
  padding: 0.5rem 1rem;
  background-color: #3b82f6;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.confirmation {
  margin-top: 1rem;
  color: green;
}
</style>
