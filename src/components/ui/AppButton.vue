<script setup>
defineProps({
  variant: {
    type: String,
    default: 'primary' // 'primary' | 'secondary'
  },
  type: {
    type: String,
    default: 'button'
  }
});
</script>

<template>
  <button :type="type" :class="['app-button', `app-button--${variant}`]">
    <slot />
  </button>
</template>

<style scoped>
.app-button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: var(--space-2);
  padding: var(--space-3) var(--space-6);
  border-radius: 12px;
  font-size: 0.95rem;
  font-weight: 600;
  cursor: pointer;
  border: 1px solid transparent;
  transition: background-color 0.2s, transform 0.1s, box-shadow 0.2s;
}

.app-button:active:not(:disabled) {
  transform: scale(0.98);
}

.app-button--primary {
  background: var(--primary);
  color: white;
  box-shadow: 0 4px 12px rgba(102, 68, 255, 0.25);
}

.app-button--primary:hover:not(:disabled) {
  background: var(--primary-hover);
}

.app-button--secondary {
  background: var(--bg-light);
  color: var(--text-muted);
  border-color: var(--border-color);
}

.app-button--secondary:hover:not(:disabled) {
  background: #e9ecef;
  color: var(--text-main);
}

.app-button:disabled {
  cursor: not-allowed;
}
</style>
