<script setup>
import { useForm, Link } from '@inertiajs/vue3'

const form = useForm({
  name: '',
  email: '',
  phone: '',
  dob: ''
})
</script>

<template>
  <div class="p-6 max-w-xl">
    <h1 class="text-xl font-bold mb-4">Add Member</h1>

    <form @submit.prevent="form.post('/members')">
      <input v-model="form.name" placeholder="Name" class="input" />
      <input v-model="form.email" placeholder="Email" class="input" />
      <input v-model="form.phone" placeholder="Phone" class="input" />
      <input v-model="form.dob" type="date" class="input" />

      <div class="mt-4 space-x-2">
        <button class="bg-blue-600 text-white px-4 py-2 rounded">Save</button>
        <Link href="/members">Cancel</Link>
      </div>
    </form>
  </div>
</template>

<style scoped>
.input {
  display: block;
  width: 100%;
  margin-bottom: 10px;
  padding: 8px;
  border: 1px solid #ccc;
}
</style>
