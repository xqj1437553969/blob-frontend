<template>
  <Layout>
    <div class="container">
      <Hero />
      <ProjectsGrid :projects="$page.projects.edges" />
    </div>
    <LatestJournals :journals="$page.journals.edges" />
  </Layout>
</template>
<page-query>
query{
  projects: allStrapiProjectpost{
    edges{
      node{
        id,
        mypath,
        title,
        date,
        thumbnail{
          url
        },
        tags{
          tag
        }
      }
    }
  }
  journals: allStrapiJournalpost{
    edges{
      node{
        id,
        mypath,
        title,
      }
    }
  }
}
</page-query>
<script>
import Hero from "@/components/Hero"
import ProjectsGrid from "@/components/ProjectsGrid"
import LatestJournals from "@/components/LatestJournals"

export default {
  components: {
    Hero,
    ProjectsGrid,
    LatestJournals
  }
}
</script>
