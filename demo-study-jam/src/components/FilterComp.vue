<script>
export default{
    emits: ['filter']
}
</script>

<template>
    <div class="flex justify-start">
        <button @click="$emit('filter')"  class="bg-blue-500 text-white px-4 py-2 rounded-lg border">Filter</button>
    </div>
</template>