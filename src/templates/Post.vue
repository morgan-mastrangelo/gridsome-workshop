<template>
  <Layout>
    <!--Title-->
    <div class="text-center pt-16 md:pt-32">
      <p class="text-sm md:text-base text-teal-500 font-bold">
        {{ $page.post.date }} <span class="text-gray-900"></span>
      </p>
      <h1 class="font-bold break-normal text-3xl md:text-5xl">
        {{ $page.post.title }}
      </h1>
    </div>
    <!-- {{ $page.post.image }} -->
    <!--image-->
    <div
      class="container w-full max-w-6xl mx-auto bg-white bg-cover mt-8 rounded"
      :style="{
        backgroundImage: `url(` + $page.post.image.src + `)`,
        height: `75vh`
      }"
    ></div>

    <!--Container-->
    <div class="container max-w-5xl mx-auto -mt-32">
      <div class="mx-0 sm:mx-6">
        <div
          class="bg-white w-full p-8 md:p-24 text-xl md:text-2xl text-gray-800 leading-normal markdown"
          style="font-family:Georgia,serif;"
          v-html="$page.post.content"
        >
          <!--Post Content-->

          <!--/ Post Content-->
        </div>
      </div>
    </div>
  </Layout>
</template>

<script>
export default {
  metaInfo() {
    return {
      title: this.$page.post.title,
      meta: [
        {
          name: "description",
          content: this.$page.post.description
        },
        { property: "og:title", content: this.$page.post.title },
        { property: "og:description", content: this.$page.post.description },
        { property: "og:image", content: this.$page.post.image.src }
      ]
    };
  }
};
</script>

<page-query>
query Post ($id: ID!) {
  post: post (id: $id) {
    author
    title
    path
    date (format: "DD/MM/YYYY")
    timeToRead
    description
    content
    image (width: 860, blur: 10)
  }
}
</page-query>

<style lang="scss"></style>
