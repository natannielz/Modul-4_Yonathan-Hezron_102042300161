<script setup>
const model = defineModel({ type: String, default: '' });
</script>

<template>
  <div class="search-bar">
    <span class="search-icon">🔍</span>
    <input
      v-model="model"
      type="text"
      class="search-input"
      placeholder="Search events by title or location..."
    />
  </div>
</template>

<style scoped>
.search-bar {
  display: flex;
  align-items: center;
  gap: var(--space-3);
  background: white;
  border: 1px solid var(--border-color);
  border-radius: 12px;
  padding: var(--space-3) var(--space-4);
  margin-bottom: var(--space-4);
  transition: border-color 0.2s;
}

.search-bar:focus-within {
  border-color: var(--primary);
}

.search-input {
  flex: 1;
  border: none;
  outline: none;
  font-size: 1rem;
  background: transparent;
}
</style>
