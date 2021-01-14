<template>
  <div class="flex flex-row h-screen bg-gray-200">
    <div class="flex flex-col justify-between items-center flex-none w-16">
      <div class="flex flex-col space-y-4 w-full items-center pt-5">
        <template v-for="index in 6" :key="index">
          <a v-if="index !== 2"><user-icon></user-icon></a>
          <template v-else>
            <a class="relative h-16 w-full flex justify-center items-center">
              <inbox-icon :size="8"></inbox-icon>
              <div
                class="absolute top-0 right-0 mr-3 mt-3 bg-red-500 w-4 h-4 text-xs text-white rounded-full text-center"
              >
                5
              </div>
            </a>
          </template>
        </template>
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
      <div class="w-3/5 border-l border-r border-gray-400 flex flex-col">
        <div
          class="flex-none h-20 flex flex-row justify-between items-center p-5 border-b"
        >
          <div class="flex flex-col space-y-1">
            <strong>Nikola Tesla</strong>
            <input
              type="text"
              class="text-sm outline-none border-b border-dashed text-gray-600 placeholder-gray-600"
              placeholder="Add conversation title"
            />
          </div>
          <div class="flex flex-row items-center">
            <star-icon></star-icon>
            <star-icon></star-icon>
            <star-icon></star-icon>
            <star-icon></star-icon>
          </div>
        </div>
        <div
          class="flex-auto overflow-y-auto p-5 space-y-4"
          style="
            background-image: url(https://static.intercomassets.com/ember/assets/images/messenger-backgrounds/background-1-99a36524645be823aabcd0e673cb47f8.png);
          "
        >
          <template v-for="i in 20" :key="i">
            <div
              v-if="i === 10"
              class="flex flex-row justify-center text-sm text-gray-500"
            >
              You assigned this conversation to yourself 5d ago
            </div>
            <div
              class="flex flex-row space-x-2"
              :class="{ 'flex-row-reverse space-x-reverse': i % 2 === 0 }"
            >
              <user-circle-icon></user-circle-icon>
              <div class="flex flex-col">
                <div
                  class="rounded p-5"
                  :class="{
                    'bg-blue-100': i % 2 === 0,
                    'bg-gray-200': i % 2 !== 0,
                  }"
                >
                  Some message text
                </div>
                <div class="text-sm text-gray-500">5 hr ago</div>
              </div>
            </div>
          </template>
        </div>
        <div class="flex-none h-40 p-4 pt-0">
          <textarea
            class="w-full h-full resize-none outline-none border focus:border-blue-600 hover:border-blue-600 rounded p-4 shadow-lg"
          >
Hi</textarea
          >
        </div>
      </div>
      <div class="w-1/5 bg-gray-200 overflow-y-auto flex flex-col">
        <div class="h-64 flex-none border-b border-gray-500"></div>
        <div class="flex flex-col space-y-4 p-4">
          <card v-for="i in 100" :key="i">Card Content</card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import UserIcon from "./components/UserIcon.vue";
import UserCircleIcon from "./icons/UserCircleIcon.vue";
import SearchIcon from "./icons/SearchIcon.vue";
import StarIcon from "./icons/StarIcon.vue";
import ConversationCard from "./components/ConversationCard.vue";
import Card from "./components/Card.vue";
import InboxIcon from "./icons/InboxIcon.vue";
export default {
  components: {
    UserIcon,
    UserCircleIcon,
    SearchIcon,
    StarIcon,
    ConversationCard,
    Card,
    InboxIcon,
  },
};
</script>

<style>
</style>