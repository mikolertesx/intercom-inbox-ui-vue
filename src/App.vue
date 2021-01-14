<template>
  <div class="flex flex-row h-screen bg-gray-200">
    <div class="flex flex-col justify-between items-center flex-none w-16 p-4">
      <div class="flex flex-col space-y-4">
        <user-icon v-for="index in 6" :key="index"></user-icon>
      </div>
      <div class="flex flex-col space-y-4">
        <user-icon v-for="index in 3" :key="index"></user-icon>
      </div>
    </div>
    <div class="w-64 bg-gray-100 p-4 flex flex-none flex-col space-y-4">
      <div class="flex flex-row justify-between items-center mb-6">
        <h1 class="text-2xl semi-bold">Inbox</h1>
        <search-icon :size="6" class="cursor-pointer"></search-icon>
      </div>
      <div class="bg-red-200 h-64"></div>
      <div class="bg-red-200 h-64"></div>
    </div>
    <div
      class="flex flex-row flex-auto bg-white rounded-tl-xl border-l shadow-xl"
    >
      <div class="flex flex-col w-1/5">
        <div class="flex-none h-24 bg-red-200">Top</div>
        <div class="flex-auto overflow-y-auto">
          <conversation-card
            v-for="index in 100"
            :key="index"
            :active="index === 1"
          ></conversation-card>
        </div>
      </div>
      <div class="w-3/5 border-l border-r border-gray-400">center</div>
      <div class="w-1/5 bg-gray-200">right</div>
    </div>
  </div>
</template>

<script>
import UserIcon from "./components/UserIcon.vue";
import SearchIcon from "./icons/SearchIcon.vue";
import ConversationCard from "./components/ConversationCard.vue";
export default {
  components: {
    UserIcon,
    SearchIcon,
    ConversationCard,
  },
};
</script>

<style>
</style>