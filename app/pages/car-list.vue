<template>
  <div class="relative">
    <button class="bg-red-600 cursor-pointer" @click="showAddCarModal">
      Add new car
    </button>
    <ul class="flex gap-4">
      <li>Audi</li>
      <li>A4</li>
      <li>2015</li>
    </ul>

    <div
      v-if="isAddCarModalVisible"
      class="absolute top-0 left-0 w-screen h-screen bg-black/30"
    >
      <div
        class="bg-white absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 p-4 rounded-4xl flex flex-col gap-4"
      >
        <button class="ml-auto" @click="closeAddCarModal">x</button>
        <p>Add car modal</p>
        <form @submit.prevent="console.log(342)">
          <input placeholder="Car mark" v-model="mark" type="text" />

          <button>Add car</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
const isAddCarModalVisible = ref(false);
const mark = ref("");

function showAddCarModal() {
  isAddCarModalVisible.value = true;
}

function closeAddCarModal() {
  isAddCarModalVisible.value = false;
}
</script>
