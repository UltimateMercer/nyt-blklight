<template>
  <div>
    <Info />
    <div class="container">
      <div class="col-12 p-0">
        <h2 class="marker marker-dark marker-title mb-4">
          <strong>
            Top Stories: World
          </strong>
        </h2>
        <div class="row">
          <div
            v-for="(widercard, i) in widercards"
            :key="i"
            class="col-lg-6 col-md-8 col-12 offset-lg-0 offset-md-2"
          >
            <WiderCards :widerCard="widercard" />
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
import WiderCards from "@/components/WiderCards.vue";

export default {
  name: "World",
  components: {
    WiderCards,
    Info,
  },

  data() {
    return {
      widercards: [],
    };
  },

  async created() {
    const res = await axios.get(
      "https://api.nytimes.com/svc/topstories/v2/world.json?api-key=oPWIpYcGwSdzOH2cqYKkyvcotJCkGRNn"
    );
    this.widercards = res.data.results;
  },
};
</script>
