<script setup lang="ts">
import { ref, computed } from 'vue'
import emailjs from '@emailjs/browser'

const form = ref({ name: '', email: '', phone: '', message: '' })
const userAnswer = ref('')
const submitted = ref(false)
const loading = ref(false)
const errors = ref<Record<string, string>>({})

const num1 = 4, num2 = 8
const challenge = `What is ${num1} + ${num2}?`
const isCorrect = computed(() => parseInt(userAnswer.value) === num1 + num2)

function validate() {
  const e: Record<string, string> = {}
  if (!form.value.name.trim()) e.name = 'Name is required.'
  if (!form.value.message.trim()) e.message = 'Message is required.'
  if (!form.value.email.trim() && !form.value.phone.trim()) e.contact = 'Email or Phone is required.'
  if (!isCorrect.value) e.challenge = 'Incorrect answer.'
  errors.value = e
  return Object.keys(e).length === 0
}

async function handleSubmit() {
  if (!validate()) return
  loading.value = true
  try {
    await emailjs.send(
      'service_r6makok',
      'template_o8442hm',
      {
        name: form.value.name,
        email: form.value.email,
        contact: form.value.phone,
        message: form.value.message,
      },
      'DB3lhKpsZpgvpCrFE'
    )
    submitted.value = true
    form.value = { name: '', email: '', phone: '', message: '' }
    userAnswer.value = ''
  } catch (e) {
    alert('Failed to send message. Please try again.')
  } finally {
    loading.value = false
  }
}
</script>

<template>
  <section id="contact">
    <div class="contact-wrapper">
      <p class="subtitle">Contact me</p>
      <h1>Get in Touch</h1>

      <div v-if="submitted" class="success">Message sent successfully!</div>

      <form @submit.prevent="handleSubmit">
        <div class="row">
          <div class="field">
            <label>Name</label>
            <input v-model="form.name" type="text" placeholder="Full Name" />
            <span v-if="errors.name" class="error">{{ errors.name }}</span>
          </div>
          <div class="field">
            <label>Email</label>
            <input v-model="form.email" type="email" placeholder="Email Address" />
          </div>
        </div>

        <div class="field">
          <label>Phone no</label>
          <input v-model="form.phone" type="tel" placeholder="Phone Number" />
          <span v-if="errors.contact" class="error">{{ errors.contact }}</span>
        </div>

        <div class="field">
          <label>Message</label>
          <textarea v-model="form.message" placeholder="Your Message" rows="5"></textarea>
          <span v-if="errors.message" class="error">{{ errors.message }}</span>
        </div>

        <div class="field">
          <label>Challenge: {{ challenge }}</label>
          <input v-model="userAnswer" type="number" placeholder="Your answer" />
          <span v-if="errors.challenge" class="error">{{ errors.challenge }}</span>
        </div>

        <button type="submit" :disabled="loading">{{ loading ? 'Sending...' : 'Submit' }}</button>
      </form>
    </div>
  </section>
</template>

<style scoped>
#contact {
  padding: 60px 20px;
  display: flex;
  justify-content: center;
}

.contact-wrapper {
  width: 100%;
  max-width: 700px;
}

.subtitle {
  color: #888;
  text-transform: uppercase;
  letter-spacing: 2px;
  font-size: 0.85rem;
  margin-bottom: 4px;
}

h1 {
  font-size: 2rem;
  margin-bottom: 20px;
}

.row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 16px;
}

.field {
  display: flex;
  flex-direction: column;
  margin-bottom: 16px;
}

label {
  font-size: 0.9rem;
  margin-bottom: 6px;
  font-weight: 500;
}

input, textarea {
  padding: 10px 14px;
  border: 1px solid #ccc;
  border-radius: 6px;
  font-size: 0.95rem;
  outline: none;
  transition: border-color 0.2s;
}

input:focus, textarea:focus {
  border-color: #555;
}

button {
  padding: 12px 32px;
  background: #222;
  color: #fff;
  border: none;
  border-radius: 6px;
  font-size: 1rem;
  cursor: pointer;
  transition: background 0.2s;
}

button:hover {
  background: #444;
}

.success {
  color: green;
  margin-bottom: 16px;
  font-weight: 500;
}

.error {
  color: red;
  font-size: 0.8rem;
  margin-top: 4px;
}
</style>
