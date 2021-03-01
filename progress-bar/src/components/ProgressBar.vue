<template>
  <div class="progress-bar">
    <h6 class="progress-bar__content__title">YOUR CURRENT USAGE</h6>
    <div
      v-for="count in counts"
      :key="count.details"
      class="progress-bar__content"
    >
      <p>
        <span class="progress-bar__content__counts">{{ count.counts }}</span>
        {{ count.details }}
      </p>

      <div class="progress-bar__item">
        <div
          class="bar"
          :style="{ background: count.color, width: count.counts / 10 + '%' }"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProgressBar",
  counts: [],
  data() {
    this.counts = [
      {
        counts: 20,
        color: "#1D97FF",
        details:
          "out of 1000 shipments. You’ve already used up to 8% of your monthly shipping allowance.",
      },
      {
        counts: 508,
        color: "#FF9F2F",
        details:
          "out of 1000 shipments. You’ve already used up to more than 50% of your monthly shipping allowance. For more information, please visit our help center.",
      },
      {
        counts: 1000,
        color: "#B50000",
        details:
          "out of 1000 shipments. You’ve already used up to more than 80% of your monthly shipping allowance. Upgrade your plan to avoid overcharge on shipments. For more information, please visit our help center.",
      },
    ];
  },
};
</script>

<style lang="scss" scoped>
$stepper-bar-height: 3px;

.progress-bar {
  background: #ffffff;
  border: 1px solid #dde4e9;
  box-sizing: border-box;
  border-radius: 6px;
  padding: 24px;

  .progress-bar__content__title {
    font-size: 14px;
    line-height: 18px;
    color: #686868;
    margin: 0;
  }
  .progress-bar__content {
    font-size: 15px;

    color: #212121;
    .progress-bar__content__counts {
      font-weight: 700;
      font-size: 25px;
      line-height: 31px;
    }
    .progress-bar__item {
      border: 1px solid #192956;
      box-sizing: border-box;
      border-radius: 20px;
      height: 16px;
      width: 100%;
      .bar {
        height: 100%;
        border-radius: 20px;
      }
    }
  }
}
</style>
