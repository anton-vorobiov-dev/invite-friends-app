<template>
  <button class="app-button" :class="`app-button--${theme}`">
    <slot></slot>
  </button>
</template>

<script setup>
defineProps({
  theme: {
    type: String,
    default: "yellow", // Значение по умолчанию
    validator: (value) => ["yellow", "blue"].includes(value), // Разрешённые значения
  },
});
</script>

<style scoped lang="scss">
.app-button {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  padding: 0px 18px;
  gap: 4px;

  min-height: 30px;
  border-radius: 12px;
  border: none;
  cursor: pointer;
  position: relative; /* Для псевдоэлемента */
  transition: all 0.3s ease-in-out;

  /* Общий эффект нажатия и наведения */
  &:hover {
    filter: brightness(1.1);
  }

  &:active {
    transform: scale(0.95);
  }

  &::after {
    content: "";
    position: absolute;
    top: 1px;
    right: 5px;
    width: 10px;
    height: 5px;
    background: #ffeeba;
    transform: rotate(18deg);
    border-radius: 50%;
  }
  /* Цветовая тема: жёлтая */
  &--yellow {
    background: linear-gradient(180deg, #f7cb40 0%, #ddad1c 100%);
    box-shadow: 0px 1px 1px rgba(0, 0, 0, 0.25), inset 0px 2px 0px #ffeeba, inset 0px -2px 0px #7a5d00;

    &::after {
      background: #ffeeba;
    }
  }

  /* Цветовая тема: синяя */
  &--blue {
    background: linear-gradient(180deg, #44a2e5 0%, #2e7ec2 100%);
    box-shadow: 0px 1px 1px rgba(0, 0, 0, 0.25), inset 0px 2px 0px #a3cdff, inset 0px -2px 0px #174590;

    &::after {
      background: #a3cdff;
    }
  }
}
</style>
