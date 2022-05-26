<script>
export default {
  props: {
    queryString: String
  },
  data() {
    return {
      gif: this.getGif(),
    };
  },
  methods: {
    getGif() {
      console.log(this.queryString);
      let url =
        `https://api.giphy.com/v1/gifs/search?api_key=90wSzGG2LBVzDYX2DwD1hn4xQFTPvXK0&q=${this.queryString}&limit=25&offset=0&rating=g&lang=en`;
      fetch(url)
        .then((response) => response.json())
        .then((data) => {
          let rand = Math.floor(Math.random() * 25);
          this.gif = data.data[rand].images.original.url;
        })
        .catch((error) => console.log(error));
    },
  },
};
</script>

<template>

  <div class="gif">
    <img alt="Gif" class="giphy" :src="gif" width="200" height="200" />
  </div>
</template>

