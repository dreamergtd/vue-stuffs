<template>
  <div class="container">
    <h1>{{welcome}}</h1>
    <div class="row">
      <div class="col-md-4 col-lg-4" v-for="(stuff, index) in this.stuffs" :key="stuff.id">
        <a @click="stuffDetails(index)">{{stuff.name}}</a>
        
      </div>
    </div>
    <router-link to="/about">
      <span class="btn btn-primary">About me.</span>
    </router-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      welcome: "Welcome to the Vue.js Stuffs!",
      stuffs: [
        {
          id: 41,
          name: "stuff 41",
          image: "https://api.adorable.io/avatars/285/abott@01.png"
        },
        {
          id: 42,
          name: "stuff 42",
          image: "https://api.adorable.io/avatars/285/abott@42.png"
        },
        {
          id: 43,
          name: "stuff 43",
          image: "https://api.adorable.io/avatars/285/abott@43.png"
        }
      ]
    };
  },
  methods: {
    stuffDetails(index) {
      const id = this.stuffs[index].id;
      this.$router.push({
        name: "Stuff",
        params: { id: id }
      });
    }
  }
};
</script>