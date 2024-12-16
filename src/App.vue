<script setup lang="ts">
import { defineAsyncComponent, ref, onMounted } from "vue";
const AppTitle = defineAsyncComponent(() => import("@/components/AppTitle.vue"));
const AppMain = defineAsyncComponent(() => import("@/components/AppMain.vue"));
const FriendsList = defineAsyncComponent(() => import("@/components/FriendsList.vue"));

const invitedFriends = ref([]);

onMounted(async () => {
  try {
    const response = await fetch("/invited_friends.json");
    invitedFriends.value = await response.json();
    console.log(invitedFriends.value);
  } catch (error) {
    console.error("Error loading friends:", error);
  }
});
</script>

<template>
  <div class="app">
    <AppTitle></AppTitle>
    <AppMain></AppMain>
    <FriendsList></FriendsList>
  </div>
</template>

<style lang="scss">
body {
  position: relative;
  width: 100dvw;
  height: 100dvh;
  overflow-y: scroll;
  background: radial-gradient(50% 50% at 50% 50%, #41aee7 0%, #054ba6 100%);
}
.app {
  display: flex;
  flex-direction: column;
  row-gap: 12px;
}
</style>
