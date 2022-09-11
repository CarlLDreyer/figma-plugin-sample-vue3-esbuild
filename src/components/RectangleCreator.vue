<template>
  <main>
    <header>
      <img :src="logoPng" />
      &nbsp;
      <img :src="`data:image/svg+xml;utf8,${logoSvg}`" />
      &nbsp;
      <Logo />
      <h2>Rectangle Creator</h2>
    </header>
    <section>
      <input
        id="input"
        v-model="input"
        type="number"
        min="0"
      />
      <label htmlFor="input">Rectangle Count</label>
    </section>
    <footer>
      <button class="brand" @click="handleCreate">Create</button>
      <button @click="handleCancel">Cancel</button>
    </footer>
  </main>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import logoPng from '../assets/logo.png'
import logoSvg from '../assets/logo.svg?raw'
import Logo from '../assets/logo.svg'

const input = ref(0)

const handleCreate = () => {
  parent.postMessage(
    { pluginMessage: { type: 'create-rectangles', count: input.value } },
    '*'
  )
}

const handleCancel = () => {
  parent.postMessage({ pluginMessage: { type: 'cancel' } }, '*')
}
</script>

<style scoped>
button {
  border-radius: 0.25rem;
  background: var(--color-bg);
  color: var(--color-text);
  cursor: pointer;
  border: 1px solid var(--color-border);
  padding: 0.5rem 1rem;
}
button:hover {
  background-color: var(--color-bg-hover);
}
button:active {
  background-color: var(--color-bg-active);
}
button:focus-visible {
  border: none;
  outline-color: var(--color-border-focus);
}
button.brand {
  --color-bg: var(--color-bg-brand);
  --color-text: var(--color-text-brand);
  --color-bg-hover: var(--color-bg-brand-hover);
  --color-bg-active: var(--color-bg-brand-active);
  --color-border: transparent;
  --color-border-focus: var(--color-border-brand-focus);
}

input {
  background: 1px solid var(--color-bg);
  border: 1px solid var(--color-border);
  color: 1px solid var(--color-text);
  padding: 0.5rem;
}

input:focus-visible {
  border-color: var(--color-border-focus);
  outline-color: var(--color-border-focus);
}

svg {
  stroke: var(--color-icon, rgba(0, 0, 0, 0.9));
}

main {
  align-items: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

section {
  align-items: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin-bottom: 1rem;
}
section > * + * {
  margin-top: 0.5rem;
}
footer > * + * {
  margin-left: 0.5rem;
}

img {
  height: auto;
  width: 2rem;
}
</style>
