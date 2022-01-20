<template>
<div class="p-4 rounded-lg shadow-lg bg-blue-20 ma-20">
    <div class="h-98">
      <div class="h-20">
        <a
            class="text-l text-center text-pink-700 hover:text-gray-300 hover:underline"
            :href="post.url"
            target="_blank"
            rel="noreferrer">

            {{ post.title }}
        </a>
      </div>

      <div class="w-full">
        <img class="w-full mt-2 rounded" :src="post.thumbnail" alt="post.thumbnail" height="140" width="120">
      </div>

      <div>
        <p class="mt-2 text-justify text-gray-600 line-clamp-4">
          {{ post.abstract }}
        </p>
      </div>
    </div>
    <p class="mt-2 font-weight-bold text-gray-600">{{post.byline}}</p>
    <p class="font-light text-gray-600">{{ formatDate(post.published_date) }}</p>
  </div>

</template>

<script>
  import {format} from "date-fns"

  export default {
  name: "NewsCard",
  props: {
    post: {
      type: Object,
      required: true,
    },
  },

  methods: {
    formatDate(strDate){
      return format(new Date(strDate), "MM do yy")
    },
  },
}
</script>

<style scoped>

</style>