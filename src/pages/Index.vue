<template>
  <Layout>
    
    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <g-image alt="Example image" src="~/favicon.png" width="135" />
    
    <h1>Hello, world!</h1>
   
    <p>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur excepturi labore tempore expedita, et iste tenetur suscipit explicabo! Dolores, aperiam non officia eos quod asperiores
    </p>

    <p class="home-links">
      <a href="https://gridsome.org/docs" target="_blank" rel="noopener">Gridsome Docs</a>
      <a href="https://github.com/gridsome/gridsome" target="_blank" rel="noopener">GitHub</a>
    </p>

    <div class="content">
      <div class="card" v-for="edge in $page.allFaker.edges" :key="edge.node.id">
        <div class="card-content columns">
        <div class="column is-2">
          <figure class="image is-128x128">
            <img class="is-rounded" :src="edge.node.avatar">
          </figure>
        </div>
        <div class="column">
          <p class="title"> {{ edge.node.author }}</p>
          <p class="subtitle"> <i class="has-text-dark">Contact Email:</i> {{ edge.node.email.src }}</p>
          <p class="subtitle"> <i class="has-text-dark"> Profile: </i> {{ edge.node.title }}</p>
        </div>
        </div>
      </div>
    </div>

  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: 'Hello, world!'
  }
}
</script>

<page-query>
query allFaker {
  allFaker (perPage: 5) {
    edges {
      node {
        email,
        author,
        avatar,
        title,
      }
    }
  }
}
</page-query>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
