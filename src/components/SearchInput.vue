<template>
  <form @submit.prevent="search" class="max-w-md px-4 mx-auto mt-12">
    <div class="relative">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="absolute top-0 bottom-0 w-6 h-6 my-auto text-gray-400 left-3"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
      >
        <path
          strokeLinecap="round"
          strokeLinejoin="round"
          strokeWidth="{2}"
          d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
        />
      </svg>
      <input
        ref="input"
        id="search"
        type="text"
        v-model="toSearch"
        placeholder="Search"
        class="w-full py-3 pl-12 pr-4 text-gray-500 border rounded-md outline-none bg-gray-50 focus:bg-white focus:border-indigo-600"
      />
    </div>
  </form>
</template>

<script lang="ts">
import { defineComponent } from "@vue/runtime-core";

export default defineComponent({
  props: {
    winner: {
      type: Boolean,
      requerid: true,
    },
  },
  data() {
    return {
      toSearch: "",
    };
  },
  methods: {
    search() {
      const ref = this.$refs["input"] as HTMLElement;
      ref.blur();
      this.$emit("search", this.toSearch);
      this.toSearch = "";
    },
  },
});
</script>

<style></style>
