<template>
<div>
  <div class="w-50 p-3 mt-4 bg-green rounded shadow-sm p-10 p-lg-15 mx-auto text-center">
    <form v-on:submit.prevent="search">
      <div class="form-group">
        <label for="artist">Artist</label>
        <input
          type="text"
          class="form-control"
          id="artist"
          aria-describedby="Insert artist"
          placeholder="Enter Artist or Band"
          v-model="form.artist"
        />
      </div>
      <div class="form-group">
        <label for="title">Title</label>
        <input
          type="text"
          class="form-control"
          id="title"
          placeholder="Masukan judul lagu"
          v-model="form.title"
        />
      </div>
      <button type="submit" class="btn btn-primary mt-4">Search</button>
    </form>
  </div>
  <div class="w-50 p-3 mt-4 bg-green rounded shadow-sm p-10 p-lg-15 mx-auto text-center">
    {{ articles }}
  </div>
</div>
</template>

<script>
export default {
  data() {
    return {
      articles: "",
      form: {
        artist: "",
        title: "",
      },
      a1: "coldplay",
      t1: "yellow",
    };
  },

  mounted() {
    console.log("Artikel : ", this.articles);
  },
  methods: {
    async search() {
      await this.$axios
        .get(this.form.artist + "/" + this.form.title)
        .then((res) => (this.articles = res.data.lyrics));
    },
  },
};
</script>
