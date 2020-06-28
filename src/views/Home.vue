<template>
  <section>
    <div class="container">
      <div class="row">
        <div class="col d-flex justify-content-center">
          <h1>Undabot - Frontend Recruitment Test</h1>
        </div>
      </div>
      <div class="row d-flex">
        <div class="col">
          <img src="./../assets/undabot-cover.png" alt="undabot cover" class="home__cover" />
          <p class="text-left">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eligendi perferendis beatae porro illo, blanditiis
            consectetur excepturi eaque sint eius dolores atque, saepe id soluta quia, repellat aspernatur minima nam quod.
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eligendi perferendis beatae porro illo, blanditiis
            consectetur excepturi eaque sint eius dolores atque, saepe id soluta quia, repellat aspernatur minima nam quod.
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eligendi perferendis beatae porro illo, blanditiis
            consectetur excepturi eaque sint eius dolores atque, saepe id soluta quia, repellat aspernatur minima nam quod.
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eligendi perferendis beatae porro illo, blanditiis
            consectetur excepturi eaque sint eius dolores atque, saepe id soluta quia, repellat aspernatur minima nam quod.
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eligendi perferendis beatae porro illo, blanditiis
            consectetur excepturi eaque sint eius dolores atque, saepe id soluta quia, repellat aspernatur minima nam quod.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Home"
};
</script>

<style lang="scss">
.home {
  &__title {
    display: flex;
    margin: 0 10px 0 0;
  }

  &__cover {
    // max-height: 50px;
    // max-width: 50px;
    float: left;
    margin-right: 10px;
    max-width: 100%;
  }
}
</style>