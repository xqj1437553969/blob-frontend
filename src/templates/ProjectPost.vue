<template>
  <Layout>
    <div class="project">
      <div class="container">
        <div class="project-header">
          <h1 class="project-title" v-html="$page.post.title" />
          <div class="project-info">
            <div class="categories-container">
              <div class="categories">
                <span class="label">Categories</span>
                <span
                  class="category"
                  v-for="(item, index) in $page.post.tags"
                  :key="index"
                  v-text="item.tag"
                />
              </div>
            </div>

            <div class="year-container">
              <span class="label">Year</span>
              <div v-html="$page.post.date" />
            </div>
          </div>
        </div>

        <div class="content">
          <p v-html="$page.post.content"></p>
          <img :src="GRIDSOME_API_URL + $page.post.thumbnail.url" alt="">
        </div>

      </div>
    </div>
  </Layout>
</template>

<page-query>
query ($id: ID!) {
  post: strapiProjectpost (id: $id) {
    title,
    date,
    content,
    thumbnail{
      url
    },
    tags{
      tag
    }
  }
}
</page-query>

<script>
export default {
  metaInfo() {
    return {
      title: this.$page.post.title
    };
  },
};
</script>

<style scoped>
.project-header {
  padding: 20vh 0 4rem 0;
}
.project-title {
  font-size: 4rem;
  margin: 0 0 4rem 0;
  padding: 0;
}
.project-info {
  display: flex;
  flex-wrap: wrap;
  font-size: 0.8rem;
}
.project-info > div {
  margin-right: 4rem;
}
.project-info > div:last-of-type {
  margin: 0;
}
.category:after {
  content: ', ';
}
.category:last-of-type:after {
  content: '';
}
</style>
