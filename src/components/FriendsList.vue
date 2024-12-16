<template>
  <div class="friends-list">
    <p class="friends-list__title">List of your friends</p>
    <AppButton class="friends-list__button">
      <span>Claim</span>

      <span><img src="@/assets/images/coin.png" alt="" height="12" weight="12" srcset="" />12.5k</span>
    </AppButton>

    <AppList :friends="friends"></AppList>
  </div>
</template>

<script setup lang="ts">
import { defineAsyncComponent, ref, onMounted } from "vue";
const AppButton = defineAsyncComponent(() => import("@/components/AppButton.vue"));
const AppList = defineAsyncComponent(() => import("@/components/AppList.vue"));

type Friend = {
  name: string;
  level: number;
};

const friends = ref<Friend[]>([]); // Стан для зберігання списку друзів

onMounted(async () => {
  try {
    const response = await fetch("/data/invited_friends.json"); // Шлях до файлу у папці public
    if (!response.ok) {
      throw new Error("Failed to fetch friends data");
    }
    friends.value = await response.json();
  } catch (error) {
    console.error("Error fetching data:", error);
  }
});
</script>

<style scoped lang="scss">
@use "@/styles/variables.scss" as *;
.friends-list {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 4px;

  width: 100%;
  margin: 0 auto;

  row-gap: 8px;

  &__title {
    font-family: "Lato", sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: 16px;
    text-align: center;

    color: #ffffff;
    @include text-stroke(#000000, 0.5px, 1px);

    margin: 0;
  }
  &__button {
    width: 142px;

    > span {
      display: inline-flex;
      align-items: center;
      column-gap: 4px;
      font-family: "Movavi Grotesque", sans-serif;
      font-style: normal;
      font-weight: 900;
      font-size: 14px;
      line-height: 20px;
      /* identical to box height */
      text-align: center;
      margin: 0 auto;

      color: #fff;

      @include text-stroke(#000000, 0.3px, 1px);
    }
  }

  &__app-list {
    width: 100%;

    .app-list__item {
      width: 100%;
    }
  }
}
</style>
