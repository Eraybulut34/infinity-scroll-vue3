<template>
  <div v-if="false"></div>
</template>
<script lang="ts">
import { defineComponent, inject } from "vue";
import { useToast } from "vue-toastification";
const toast = useToast();
export default defineComponent({
  name: "InfinityScroll",
  data: () => ({
    scrollClass: inject("scrollClass") as string,
    handleScroll: inject("handleScroll") as any,
    listEnd: inject("listEnd") as boolean,
  }),
  methods: {
    setEventListener() {
      const scrollClass = document.querySelector(this.scrollClass);
      scrollClass?.addEventListener("scroll", (e: any) => {
        const { scrollTop, scrollHeight, clientHeight } = e.target as Element;
        if (scrollTop + clientHeight >= scrollHeight && !this.listEnd) {
          this.handleScroll();
        }
      });
    },
  },
  mounted() {
    setTimeout(() => {
      this.setEventListener();
    }, 100);
  },
  watch: {
    listEnd(val) {
      if (val) {
        toast.success("Liste sonuna ulaştınız.");
      }
    },
  },
});
</script>
