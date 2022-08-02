<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "Message",
  props: {
    msg: {
      type: String,
    },
  },
  setup({ msg }) {
    const msgRef = ref("");
    if (msg) {
      localStorage.setItem("msg", msg);
    }
    msgRef.value = localStorage.getItem("msg");
    return {
      msgRef,
    }
  },
});
</script>
<template>
  <h1>{{ msgRef }}</h1>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
