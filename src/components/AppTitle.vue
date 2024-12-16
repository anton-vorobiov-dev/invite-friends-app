<template>
  <div class="app-title">
    <h1 class="app-title__main-text">INVITE FRIENDS!</h1>
    <p class="app-title__sub-text">You and your friend will receive bonuses!</p>
  </div>
</template>

<style scoped lang="scss">
@use "@/styles/variables.scss" as *;
.app-title {
  display: flex;
  flex-direction: column;
  // align-items: center;
  padding: 0;

  width: 302px;
  height: 41px;
  margin: 0 auto;

  &__main-text {
    /* invite friends! */

    width: 302px;
    height: 24px;

    font-family: "Movavi Grotesque", sans-serif;
    font-style: normal;
    font-weight: 900;
    font-size: 24px;
    line-height: 24px;
    /* identical to box height */
    text-align: center;
    text-transform: uppercase;
    margin: 0 auto;

    color: #facb46;

    text-shadow: $stroke-shadow, 0px 2px 0px #000000;

    /* Inside auto layout */
    flex: none;
    order: 0;
    align-self: stretch;
    flex-grow: 0;
  }

  &__sub-text {
    font-family: "Lato", sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: 14px;
    line-height: 17px; /* Matches box height */
    text-align: center;

    color: #ffffff;
    text-shadow: 0px 1px 0px #000000;

    margin: 0;
    width: 288px;
    height: 17px;
  }
}
</style>
