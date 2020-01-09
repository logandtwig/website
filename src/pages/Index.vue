<template>
  <Layout>
    <div class="content">
      <h1 class="title">A quality driven software consultant company.</h1>

      <h3
        class="subtitle"
      >A group of skilled people that loves building great software.</h3>
    </div>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: "Home"
  }
};
</script>

<style lang="scss">
.content {
  margin-right: 4vw;
  margin-left: 4vw;
  display: flex;
  flex-direction: column;
  text-align: center;

  h3 {
    font-family: Inter-Light;
    font-weight: 300;
    font-style: normal;
    font-size: 30px;
    letter-spacing: -0.01em;
    line-height: 1.38em;
    text-transform: none;
    color: #878787;
  }

  .title {
    font-family: Inter-Medium;
    letter-spacing: 0.04em;
    line-height: 1.1em;
    color: black;
    margin-bottom: 0px;
    font-size: 60px;
  }

  @media only screen and (max-width: 600px) {
    .title {
      font-size: 40px;
    }
  }
}
</style>
