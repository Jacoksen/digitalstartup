<template>
    <div class="grid-container">
        <article v-for="post in posts" :key="post.id">
            <img :src="post.image" alt="Post Image">
            <h3>{{post.title}}</h3>
            <p>{{post.description}}</p>
            <input type="text" v-model="post.title" placeholder="Title" required>
            <input type="text" v-model="post.description" placeholder="Description" required>
            <button class="update" type="button" v-on:click="updatePost(post)">Update</button>
            <button class="delete" type="button" v-on:click="deletePost(post)">Delete</button>
        </article>
    </div>
</template>

<script>
import { postRef } from '../firebase-db'
export default {
  data () {
    return {
      posts: []
    }
  },
  firestore: {
    posts: postRef
  },
  methods: {
    deletePost (post) {
      postRef.doc(post.id).delete()
    },
    updatePost (post) {
      postRef.doc(post.id).update({ title: post.title })
      postRef.doc(post.id).update({ description: post.description })
      alert('Post updated succesfully!')
    }
  }
}
</script>

<style>
/* ---------- Grid container ---------- */
.grid-container {
  display: grid;
  grid-template-columns: 100%;
  padding: 10px;
}

@media (min-width: 600px) {
  .grid-container {
    grid-template-columns: 50% 50%;
  }
}

@media (min-width: 992px) {
  .grid-container {
    grid-template-columns: 33.33% 33.33% 33.33%;
  }
}

.grid-container > article {
  text-align: center;
  padding: 10px;
}

.grid-container > article img {
  max-width: 300px;
  width: 100%;
}

.grid-container > article h3 {
  font-weight: 200;
  margin: 0 0 1.5em;
}
</style>
