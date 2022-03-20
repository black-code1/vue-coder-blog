<template>
  <div class="home">
    <h1>Home</h1>
    <PostList v-if="showPosts" :posts="posts" />
    <button @click="showPosts = !showPosts">toggle posts</button>
    <button @click="posts.pop()">delete a post</button>
  </div>
</template>

<script>
import PostList from "../components/PostList.vue";
import { ref } from "@vue/reactivity";
// @ is an alias to /src

export default {
  name: "HomeView",
  components: { PostList },
  setup() {
    const posts = ref([
      {
        title: "welcome to the blog",
        body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex numquam natus sint, quibusdam sunt labore voluptates delectus officiis autem voluptatum unde eum ea et, fugit consectetur quia nobis vel quidem reprehenderit recusandae aliquid ipsa assumenda rerum? Nobis consequatur sit excepturi pariatur, laboriosam doloremque ex eaque aliquid officiis, non culpa voluptatibus facilis accusamus repellat recusandae quas at perspiciatis, fugit eius perferendis. Magnam ea animi et voluptate tenetur! Voluptates excepturi enim nostrum, autem labore commodi quis tenetur minus recusandae omnis ipsam neque quod, illo qui rem repudiandae laborum aspernatur culpa dignissimos consectetur, possimus unde hic. Placeat inventore consequuntur quisquam perferendis saepe sequi!",
        id: 1,
      },
      {
        title: "top 5 CSS tips",
        body: "loremipsum",
        id: 2,
      },
    ]);
    const showPosts = ref(true);
    return { posts, showPosts };
  },
};
</script>
