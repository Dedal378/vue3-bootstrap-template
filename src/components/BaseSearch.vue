<script setup>
defineProps({
  search: {
    type: Boolean,
  },
  modelValue: {
    type: String,
  },
})
defineEmits(['update:modelValue'])
</script>

<template>
  <div class="input-group w-25">
    <span v-if="search" class="input-group-text" id="basic-addon1">
      <svg
        class="bi bi-search"
        fill="currentColor"
        height="16"
        viewBox="0 0 16 16"
        width="16"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001c.03.04.062.078.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1.007 1.007 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0z"
        />
      </svg>
    </span>
    <input
      @input="$emit('update:modelValue', $event.target.value)"
      :value="modelValue"
      aria-describedby="basic-addon1"
      aria-label="Filter by author"
      class="form-control"
      placeholder="Filter by author..."
      type="text"
    />
  </div>
</template>
