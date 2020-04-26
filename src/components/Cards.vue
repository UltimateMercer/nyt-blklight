<template>
  <div class="card card-background card-featured-post view mb-3">
    <img
      :src="card.multimedia[0]['url']"
      class="card-background-image featured-image"
      alt=""
    />
    <div class="card-body h-100 d-flex flex-column justify-content-end">
      <h5 class="card-common-title">
        <span class="marker marker-dark">
          <strong>
            {{ card.title }}
          </strong>
        </span>
      </h5>
      <div class="card-subinfo">
        <span
          class="badge badge-tag badge-flat badge-uv"
          style="text-transform: capitalize"
        >
          {{ card.section }}
        </span>
        <span class="badge badge-tag badge-flat badge-dark">
          {{ dateFormat }}
        </span>
      </div>
      <a
        :href="card.short_url"
        class="stretched-link"
        target="_blank"
        rel="noopener noreferrer"
      ></a>
    </div>

    <div class="mask texture-mask-4"></div>
  </div>
</template>

<script>
import { format } from "date-fns";

export default {
  name: "Cards",
  props: {
    card: Object,
  },

  computed: {
    dateFormat() {
      const formattedDate = format(
        new Date(this.card.updated_date),
        "dd MMM yyyy"
      );
      return formattedDate;
    },
  },
};
</script>
