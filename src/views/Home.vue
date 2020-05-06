<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.svg" />
    <post-list></post-list>
  </div>
</template>

<script>
// @ is an alias to /src
import PostList from '../components/PostList.vue'

export default {
  name: 'Home',
  components: {
    PostList
  }
}
</script>

<style>
form {
  padding: 2em 1em 2.5em;
}

button {
  text-align: center;
  cursor: pointer;
  border: none;
  padding: 12px 15px;
  font-size: 1em;
  border-radius: 0;
  color: var(--text-color-light);
  background-color: var(--secondary);
  width: 100%;
  max-width: 350px;
}

article button {
  text-align: center;
  cursor: pointer;
  border: none;
  padding: 10px 8px;
  border-radius: 0;
  color: var(--text-color-light);
  background-color: var(--green);
  width: 40%;
}

button.update {
  background-color:var(--primary);
  margin:0.2em;
}

button.delete {
  background-color: #ff3d40;
}

input {
  margin: 1em auto;
  width: 100%;
  max-width: 350px;
  padding: 12px 15px;
  box-sizing: border-box;
  display: block;
}

img {
  margin: 1.2em;
}
</style>
