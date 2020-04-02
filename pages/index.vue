<template>
  <div class="min-h-screen bg-gray-200 antialiased xl:flex xl:flex-col xl:h-screen">
    <SiteHeader class="xl:flex-shrink-0" />
    <div class="xl:flex-1 xl:flex xl:overflow-y-hidden">
      <SearchFilters />
      <main class="py-6 xl:flex-1 xl:overflow-x-hidden">
        <div class="px-4">
          <h3 class="text-gray-900 text-xl">Los Angeles</h3>
          <p
            class="text-gray-600"
          >Live like the stars in thesse luxurious Southern California estates.</p>
        </div>
        <div class="sm:overflow-x-auto">
          <div class="px-4 sm:inline-flex sm:-ml-2 sm:pb-8">
            <div
              v-for="(property, i) in properties"
              :key="i"
              :class="{'mt-10' : i > 0}"
              class="sm:mt-0 sm:w-80 sm:flex-shrink-0 sm:px-2"
            >
              <PropertyCard :property="property" />
            </div>
          </div>
        </div>
      </main>
    </div>
  </div>
</template>

<script>
import SiteHeader from "@/components/SiteHeader.vue";
import SearchFilters from "@/components/SearchFilters.vue";
import PropertyCard from "@/components/PropertyCard.vue";

export default {
  components: {
    SiteHeader,
    SearchFilters,
    PropertyCard
  },
  data() {
    return {
      properties: [
        {
          imageUrl:
            "https://images.unsplash.com/photo-1512917774080-9991f1c4c750?ixlib=rb-1.2.1&auto=format&fit=crop&w=1650&q=80",
          beds: 3,
          baths: 2,
          title: "Modern Home in City Center",
          price: 140000,
          reviewCount: 34,
          rating: 4
        },
        {
          imageUrl:
            "https://images.unsplash.com/photo-1416331108676-a22ccb276e35?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1647&q=80",
          beds: 5,
          baths: 3,
          title: "Downtown Island Getaway",
          price: 160000,
          reviewCount: 17,
          rating: 5
        },
        {
          imageUrl:
            "https://images.unsplash.com/photo-1564013799919-ab600027ffc6?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1650&q=80",
          beds: 3,
          baths: 1,
          title: "Beautiful Villa near Beach",
          price: 120000,
          reviewCount: 22,
          rating: 3
        },
        {
          imageUrl:
            "https://images.unsplash.com/photo-1548386704-23fc0135faab?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1649&q=80",
          beds: 6,
          baths: 4,
          title: "California Dream Home",
          price: 250000,
          reviewCount: 12,
          rating: 3
        }
      ]
    };
  }
};
</script>
