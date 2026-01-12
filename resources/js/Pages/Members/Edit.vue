<script setup>
import { useForm, Link } from '@inertiajs/vue3'

const props = defineProps({
  member: Object
})

const form = useForm({
  name: props.member.name,
  email: props.member.email,
  phone: props.member.phone,
  dob: props.member.dob
})
</script>

<template>
  <div class="p-6 max-w-xl">
    <h1 class="text-xl font-bold mb-4">Edit Member</h1>

    <form @submit.prevent="form.put(`/members/${props.member.id}`)">
      <input v-model="form.name" class="input" />
      <input v-model="form.email" class="input" />
      <input v-model="form.phone" class="input" />
      <input v-model="form.dob" type="date" class="input" />

      <div class="mt-4 space-x-2">
        <button class="bg-blue-600 text-white px-4 py-2 rounded">Update</button>
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
