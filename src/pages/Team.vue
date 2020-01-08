<template>
  <Layout>
    <h1>The team</h1>
    <p>Here's the people behind Log & Twig</p>

    <div class="consultants">
      <div
        class="consultant"
        v-for="consultant in $page.consultants.edges"
        :key="consultant.name"
      >
      <img class="avatar" :src="consultant.node.image" />
      <h3>{{consultant.node.name}}</h3>
      <h4>{{consultant.node.title}}</h4>
      <p>{{consultant.node.description}}</p>

      </div>
    </div>
  </Layout>
</template>

<page-query>

query Consultants {
  consultants: allConsultant {
    edges {
      node {
        name
        title
        image
        description
      }
    }
  }
}

</page-query>

<script>
export default {
  metaInfo: {
    title: "About us"
  },
};
</script>

<style lang="scss">
    .consultants {
        display: flex;
        justify-items: center;
        flex-wrap: wrap;
        justify-content: center;
    }

    .consultant {
      margin: 20px;
      padding: 20px;
      box-shadow: 0 0 0 1px #E2E9ED;
      background: white;
      text-align: center;
      max-width: 200px;

      p {
        font-size: 16px;
      }
    }

    .avatar {
        width: 140px;
        height: 140px;
        border-radius: 100%;
        margin: 0 auto 20px;
        overflow: hidden;
    }
</style>
