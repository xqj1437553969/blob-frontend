<template>
    <div 
        class="journal-content"
    >
     <p v-html="content"></p>
     <img :src="GRIDSOME_API_URL + url" alt="">
    </div>
</template>

<script>
export default {
    props: {
        content: String,
        url: String
    }
}
</script>

<style>
p {
    line-height: 1.5;
    font-size: 1.15rem;
}
h2 {
    font-size: 2rem;
}
h3 {
    font-size: 1.5rem;
}
h4, h5, h6 {
    font-size: 1.15rem;
}
</style>
