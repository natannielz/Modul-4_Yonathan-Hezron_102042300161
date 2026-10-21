<script setup>
defineProps({
  categories: {
    type: Array,
    default: () => []
  }
});

const model = defineModel({ type: String, default: 'All' });
</script>

<template>
  <div class="category-filter">
    <button
      v-for="cat in categories"
      :key="cat"
      :class="['filter-chip', { active: model === cat }]"
      @click="model = cat"
    >
      {{ cat }}
    </button>
  </div>
</template>

<style scoped>
.category-filter {
  display: flex;
  flex-wrap: wrap;
  gap: var(--space-2);
}

.filter-chip {
  background: white;
  border: 1px solid var(--border-color);
  color: var(--text-muted);
  padding: var(--space-2) var(--space-4);
  border-radius: 50px;
  font-size: 0.9rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s;
}

.filter-chip:hover {
  color: var(--primary);
  border-color: var(--primary);
}

.filter-chip.active {
  background: var(--primary);
  border-color: var(--primary);
  color: white;
}
</style>
