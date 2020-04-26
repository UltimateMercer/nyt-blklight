<template>
  <div class="card my-4 mx-5">
    <!-- Card image -->
    <div class="card-picture wider view ">
      <img
        class="card-img card-img-fit rounded"
        :src="widerCard.multimedia[0]['url']"
        alt="Card image cap"
      />
      <div class="mask texture-mask-4"></div>
    </div>
    <div class="card-body">
      <h4 class="mb-2">
        <span class="marker marker-dark"> {{ widerCard.title }} </span>
      </h4>
      <p v-if="widerCard.abstract" class="card-text mb-2">
        {{ widerCard.abstract }}
      </p>
      <span
        class="badge badge-tag badge-flat badge-uv"
        style="text-transform: capitalize"
      >
        {{ widerCard.section }}
      </span>
      <span class="badge badge-tag badge-flat badge-dark">
        {{ dateFormat }}
      </span>
      <a
        :href="widerCard.short_url"
        class="stretched-link"
        target="_blank"
        rel="noopener noreferrer"
      ></a>
    </div>
  </div>
</template>

<script>
import { format } from "date-fns";

export default {
  name: "WiderCards",
  props: {
    widerCard: Object,
  },

  computed: {
    dateFormat() {
      const formattedDate = format(
        new Date(this.widerCard.updated_date),
        "dd MMMM yyyy"
      );
      return formattedDate;
    },
  },
};
</script>
