<script setup>
import AppCard from '@/components/ui/AppCard.vue';
import AppButton from '@/components/ui/AppButton.vue';

defineProps({
  event: {
    type: Object,
    required: true
  }
});

defineEmits(['view-detail']);
</script>

<template>
  <AppCard class="event-card">
    <div class="card-top">
      <span class="category-badge">{{ event.cat }}</span>
      <span class="price-tag">{{ event.price }}</span>
    </div>

    <h3 class="event-title">{{ event.title }}</h3>
    <p class="event-meta">📅 {{ event.date }}</p>
    <p class="event-meta">{{ event.loc }}</p>
    <p class="event-desc">{{ event.desc }}</p>

    <div class="card-footer">
      <span class="quota">🎟️ {{ event.quota }} seats</span>
      <AppButton variant="primary" @click="$emit('view-detail', event.id)">
        View Detail
      </AppButton>
    </div>
  </AppCard>
</template>

<style scoped>
.event-card {
  padding: var(--space-6);
  display: flex;
  flex-direction: column;
  height: 100%;
}

.event-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 24px rgba(28, 25, 72, 0.08);
}

.card-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: var(--space-3);
}

.category-badge {
  background: rgba(102, 68, 255, 0.1);
  color: var(--primary);
  padding: 4px 10px;
  border-radius: 50px;
  font-size: 0.8rem;
  font-weight: 600;
  text-transform: uppercase;
}

.price-tag {
  font-weight: 700;
  color: var(--text-main);
}

.event-title {
  font-size: 1.3rem;
  color: var(--text-main);
  margin-bottom: var(--space-2);
}

.event-meta {
  font-size: 0.9rem;
  color: var(--text-muted);
}

.event-desc {
  font-size: 0.95rem;
  color: var(--text-muted);
  margin: var(--space-3) 0 var(--space-6);
  flex-grow: 1;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

.card-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: var(--space-4);
  border-top: 1px solid var(--border-color);
}

.quota {
  font-size: 0.85rem;
  font-weight: 600;
  color: #27ae60;
}
</style>
