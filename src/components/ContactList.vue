<script>
export default {
  props: {
    constacts: { type: Array, default: [] },
    activeIndex: { type: Number, default: -1 },
  },
  emits: ["update:activeIndex"],
  methods: {
    updateActiveIndex(index) {
      this.$emit("update:activeIndex", index);
    },
  },
};
</script>

<template>
  <ul class="list-group">
    <li
      class="list-group-items"
      v-for="(constact, index) in constacts"
      :key="constact._id"
      :class="{ active: index === activeIndex }"
      @click="updateActiveIndex(index)"
    >
      {{ constact.name }}
    </li>
  </ul>
</template>
