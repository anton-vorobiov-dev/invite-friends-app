<template>
  <div class="list-container">
    <div class="list-item" v-for="(friend, index) in friends" :key="index">
      <div class="icon">
        <img src="@/assets/images/avatar-empty.png" alt="avatar" />
      </div>
      <div class="name">{{ friend.name }}</div>
      <div class="level">{{ friend.level }} lvl</div>
      <div class="bottom-border"></div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

type Friend = {
  name: string;
  level: number;
};

defineProps<{ friends: Friend[] }>();
</script>

<style scoped lang="scss">
@use "@/styles/variables.scss" as *;

.list-container {
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 9px 4px;
  gap: 8px;

  width: 100%;
  flex: 1;
  overflow-y: auto;
  max-height: 500px;
  background: radial-gradient(51.04% 70.67% at 50% 52.89%, #3081b4 0%, #19488c 100%);
  border-width: 0px 1px 1px 1px;
  border-style: solid;
  border-color: #3579b5;
  box-shadow: inset 0px 4px 4.5px rgba(0, 3, 6, 0.5);
  border-radius: 12px;

  position: relative;
}

.list-item {
  position: relative;
  box-sizing: border-box;

  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 6px 4px;
  gap: 8px;

  width: 100%;
  background: radial-gradient(51.04% 70.67% at 50% 52.89%, #3081b4 0%, #19488c 100%);

  .icon {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 30px;
    height: 30px;
    background: #15376c;
    box-shadow: 0px 1px 4px rgba(0, 174, 229, 0.5);
    border-radius: 4px;

    img {
      width: auto;
      height: 34px;
    }
  }

  .name {
    font-family: "Lato", sans-serif;
    font-weight: 600;
    font-size: 10px;
    width: 184px;
    text-align: start;
    color: #ffffff;
    @include text-stroke(#000000, 0.5px, 1px);
  }

  .level {
    font-family: "Lato", sans-serif;
    font-weight: 600;
    font-size: 16px;
    text-align: center;
    color: #ffffff;
    @include text-stroke(#000000, 0.5px, 1px);
  }

  .bottom-border {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 1px;
    background: linear-gradient(
      to right,
      rgba(167, 221, 253, 0) 0%,
      rgba(167, 222, 253, 1) 50%,
      rgba(167, 221, 253, 0) 100%
    );
    border-radius: 8px;
  }
}
</style>
