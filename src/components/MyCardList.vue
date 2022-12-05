<script>
import MyCard from "./MyCard.vue";
export default {
  components: {
    MyCard,
  },
  data() {
    return {
      playlists: [
        {
          id: 1,
          title: "Playlist Détente",
          srcImage: "http://placekitten.com/200/200",
        },
        {
          id: 2,
          title: "Mix années 90",
          srcImage: "http://placekitten.com/200/200",
        },
        {
          id: 3,
          title: "Mix années 2000",
          srcImage: "http://placekitten.com/200/200",
        },
        {
          id: 4,
          title: "Mix années 2020",
          srcImage: "http://placekitten.com/200/200",
        },
      ],
    };
  },
};
</script>

<template>
  <div class="list">
    <MyCard
      v-for="playlist in playlists"
      :key="playlist.id"
      :title="playlist.title"
      :srcImage="playlist.srcImage"
    />
  </div>
</template>

<style lang="scss" scoped>
.list {
  display: flex;
}
</style>
