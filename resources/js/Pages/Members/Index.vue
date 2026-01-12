<script setup>
import { Link, router } from '@inertiajs/vue3'

defineProps({
  members: Array
})

function destroy(id) {
  if (confirm('Delete this member?')) {
    router.delete(`/members/${id}`)
  }
}
</script>

<template>
  <div class="p-6">
    <div class="flex justify-between mb-4">
      <h1 class="text-2xl font-bold">Members</h1>
      <Link href="/members/create" class="bg-blue-600 text-white px-4 py-2 rounded">
        Add Member
      </Link>
    </div>

    <table class="w-full border">
      <thead>
        <tr class="bg-gray-100">
          <th class="p-2">Name</th>
          <th>Email</th>
          <th>Phone</th>
          <th>DOB</th>
          <th></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="m in members" :key="m.id" class="border-t">
          <td class="p-2">{{ m.name }}</td>
          <td>{{ m.email }}</td>
          <td>{{ m.phone }}</td>
          <td>{{ m.dob }}</td>
          <td class="space-x-2">
            <Link :href="`/members/${m.id}/edit`" class="text-blue-600">Edit</Link>
            <button @click="destroy(m.id)" class="text-red-600">Delete</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
