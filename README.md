# Modul 4 — Manajemen State dan Interaksi Pengguna

**Nama:** Yonathan Hezron
**NIM:** 102042300161
**Mata Kuliah:** Pengembangan UI Lanjut

Aplikasi Gatherly (Vue 3 + Vite) dengan manajemen state terpusat menggunakan Composition API.

## Fitur Modul 4
- `src/composables/useEvents.js` — Single Source of Truth, derived state (`computed`), `watch` deep ke LocalStorage
- `src/components/ui/AppModal.vue` — dialog konfirmasi dengan backdrop blur
- `src/views/Dashboard.vue` — layar pemantauan metrik & tabel status (read-only)
- `src/views/EventManagement.vue` — 3 tab: Active / Create / Completed (create, complete, delete)
- `src/views/EventList.vue` — katalog publik dari `activeEvents` + friendly empty state
- `src/views/EventDetail.vue` — detail dinamis berdasarkan `route.params.id` + 404 graceful
- `src/router/index.js` — nested route `/dashboard/events`
- `src/layouts/DashboardLayout.vue` — sidebar disederhanakan (exact-active-class)

## Menjalankan

```bash
npm install
npm run dev
```
