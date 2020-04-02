<template>
  <div>
    <div class="relative pb-5/6">
      <img
        class="absolute inset-0 rounded-lg shadow-md h-full mt-6 object-cover"
        v-bind:src="property.imageUrl"
        alt="California Home"
      />
    </div>
    <div class="relative px-4 -mt-16">
      <div class="bg-white rounded-lg px-4 py-4 shadow-lg">
        <div class="flex">
          <span
            class="inline-block bg-teal-200 text-teal-800 font-semibold uppercase tracking-wide text-xs rounded-full px-2 py-1 leading-none"
          >Plus</span>
          <div
            class="ml-2 text-xs font-semibold text-gray-600 uppercase tracking-wide"
          >{{ property.beds }} {{property.beds === 1 ? "bed" : "beds" }} &bull; {{property.baths}} {{property.baths === 1 ? "bath" : "baths" }}</div>
        </div>
        <h4 class="mt-1 text-gray-900 font-semibold text-lg">{{ property.title }}</h4>
        <div class="mt-1">
          <span class="text-gray-900">{{ formattedPrice }}</span>
          <span class="text-gray-600 text-sm tracking-wide">/wk</span>
        </div>
        <div class="flex items-center mt-2 text-sm text-gray-600">
          <svg
            v-for="i in 5"
            :key="i"
            aria-hidden="true"
            focusable="false"
            data-prefix="fas"
            data-icon="star"
            class="svg-inline--fa fa-star fa-w-18 h-4 w-4 fill-current"
            :class="property.rating >= i ? 'text-teal-500' : 'text-gray-400'"
            role="img"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 576 512"
          >
            <path
              d="M259.3 17.8L194 150.2 47.9 171.5c-26.2 3.8-36.7 36.1-17.7 54.6l105.7 103-25 145.5c-4.5 26.3 23.2 46 46.4 33.7L288 439.6l130.7 68.7c23.2 12.2 50.9-7.4 46.4-33.7l-25-145.5 105.7-103c19-18.5 8.5-50.8-17.7-54.6L382 150.2 316.7 17.8c-11.7-23.6-45.6-23.9-57.4 0z"
            />
          </svg>
          <span class="ml-2">
            <div
              class="text-sm text-gray-600"
            >{{ property.reviewCount }} {{property.reviewCount === 1 ? "Review" : "Reviews" }}</div>
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["property"],
  computed: {
    formattedPrice() {
      const formatter = new Intl.NumberFormat("en-US", {
        style: "currency",
        currency: "USD"
      });
      return formatter.format(this.property.price / 100);
    }
  }
};
</script>
