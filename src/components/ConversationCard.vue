<template>
  <a href="#" class="block border-b">
    <div :class="activeStyle">
      <div class="flex flex-flex-row items-center space-x-2">
        <user-circle-icon class="mr-2" :size="5"></user-circle-icon>
        <strong class="flex-grow text-sm">Nikola Tesla</strong>
        <div class="text-sm text-gray-600">5hr</div>
      </div>
      <div class="flex flex-row items-center space-x-1">
        <academic-cap-icon :size="3" class="mr-2"></academic-cap-icon>
        <div class="flex-grow truncate text-s">
          This text will be truncated in a very polite manner, just saying my
          dude...
        </div>
      </div>
    </div>
  </a>
</template>

<script>
import AcademicCapIcon from "../icons/AcademicCapIcon.vue";
import UserCircleIcon from "../icons/UserCircleIcon.vue";

export default {
  components: {
    AcademicCapIcon,
    UserCircleIcon,
  },
  props: {
    active: {
      type: Boolean,
      default: false,
    },
    unread: {
      type: Boolean,
      default: true,
    },
  },
  computed: {
    activeStyle() {
      return `${
        this.active
          ? "border-blue-500 bg-blue-100"
          : "border-transparent hover:bg-blue-100"
      } p-3 space-y-4 border-l-2`;
    },
  },
};
</script>