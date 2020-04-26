<template>
  <div>
    <Info />
    <div class="container-fluid">
      <div
        class="col-lg-10 col-md-12 col-10 offset-lg-1 offset-md-0 offset-1 p-0"
      >
        <h2 class="marker marker-dark marker-title">
          <strong>
            Top Stories: Home
          </strong>
        </h2>
        <div class="row">
          <div
            v-for="(card, i) in cards"
            :key="i"
            class="col-lg-4 col-md-8 col-12 offset-lg-0 offset-md-2"
          >
            <Cards :card="card" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from "axios";
import Info from "@/components/Info.vue";
import Cards from "@/components/Cards.vue";

export default {
  name: "Home",
  components: {
    Cards,
    Info,
  },

  data() {
    return {
      cards: [],
    };
  },

  async created() {
    const res = await axios.get(
      "https://api.nytimes.com/svc/topstories/v2/home.json?api-key=oPWIpYcGwSdzOH2cqYKkyvcotJCkGRNn"
    );
    this.cards = res.data.results;
  },
};
</script>
