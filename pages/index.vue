<template>
  <MainLayout>
    <div id="IndexPage" class="w-full overflow-auto">
      <div class="mx-auto max-w-[500px] overflow-hidden">
        <div id="Posts" class="px-4 max-w-[600px] mx-auto">
          <div v-if="isPost" v-for="post in posts" :key="post">
            <Post :post="post" @isDeleted="posts = []" />
          </div>
        </div>
      </div>
    </div>
  </MainLayout>
</template>

<script setup>
import MainLayout from "../layouts/MainLayout.vue";
import { useUserStore } from "../stores/user";
const userStore = useUserStore();
// const user = useSupabaseUser();

let posts = ref([]);
let isPost = ref(true);
let isLoading = ref(false);

onBeforeMount(() => {
  posts.value = [
    {
      name: "john weeks dev",
      image: "https://placeholder.co/100",
      text: "this is the title",
      picture: "https://placeholder.co/500",
    },
  ];
});
</script>
