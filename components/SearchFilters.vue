<template>
  <section class="bg-gray-800 xl:w-72">
    <div class="flex justify-between px-4 py-3 xl:hidden">
      <div class="relative max-w-xs w-full">
        <div class="absolute inset-y-0 left-0 pt-2 pl-3">
          <svg width="20" height="20" xmlns="http://www.w3.org/2000/svg">
            <path
              d="M14.32 12.906l1.096 1.096c.412-.023.83.123 1.145.437l3 3a1.5 1.5 0 01-2.122 2.122l-3-3a1.497 1.497 0 01-.437-1.145l-1.096-1.096a8 8 0 111.414-1.414zM8 14A6 6 0 108 2a6 6 0 000 12z"
              fill="#A0AEC0"
            />
          </svg>
        </div>
        <input
          class="block w-full bg-gray-900 text-white rounded-lg pl-10 pr-4 py-2 focus:outline-none focus:bg-gray-200 focus:text-gray-900"
          placeholder="Search by keywords"
        />
      </div>
      <button
        @click="toggle"
        type="button"
        class="ml-4 inline-flex bg-gray-700 border-transparent rounded-lg shadow px-3 hover:bg-gray-600 focus:outline-none focus:shadow-outline"
      >
        <div class="pt-2">
          <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg">
            <path
              d="M0 1a1 1 0 011-1h16a1 1 0 110 2H1a1 1 0 01-1-1zm3 6a1 1 0 011-1h10a1 1 0 110 2H4a1 1 0 01-1-1zm4 5a1 1 0 100 2h4a1 1 0 100-2H7z"
              fill="#A0AEC0"
            />
          </svg>
        </div>
        <span class="text-white font-medium ml-2 pt-1">Filters</span>
      </button>
    </div>
    <!-- =============================================== -->
    <form v-show="isOpen" class="xl:h-full xl:flex xl:flex-col xl:justify-between">
      <div class="lg:flex xl:block xl:overflow-y-auto">
        <div class="px-4 py-4 border-t border-gray-900 lg:w-1/3 xl:border-t-0 xl:w-full">
          <div class="flex flex-wrap sm:-mx-2">
            <label class="block w-1/2 px-2 sm:w-1/4 lg:w-1/2">
              <span class="mt-1 text-sm font-semibold text-gray-500">Bedrooms</span>
              <select
                class="form-select block w-full bg-gray-700 border-transparent rounded-lg text-white"
              >
                <option>4</option>
              </select>
            </label>
            <label class="block w-1/2 px-2 sm:w-1/4 lg:w-1/2">
              <span class="mt-1 text-sm font-semibold text-gray-500">Bathrooms</span>
              <select
                class="form-select block w-full bg-gray-700 border-transparent rounded-lg text-white"
              >
                <option>2</option>
              </select>
            </label>
            <label class="mt-4 block w-full px-2 sm:mt-0 sm:w-1/2 lg:mt-4 lg:w-full">
              <span class="mt-1 text-sm font-semibold text-gray-500">Price Range</span>
              <select
                class="form-select block w-full bg-gray-700 border-transparent rounded-lg text-white px-2"
              >
                <option>Up to $2,000/wk</option>
              </select>
            </label>
          </div>
        </div>
        <!-- ============================================= -->
        <div class="px-4 py-4 border-t border-gray-900 lg:w-1/3 lg:border-l xl:w-full">
          <span class="mt-1 text-sm font-semibold text-gray-500 block">Property Type</span>
          <div class="sm:flex sm:-mx-2 lg:block lg:mx-0">
            <label class="mt-3 sm:w-1/4 sm:px-2 flex items-center lg:px-0">
              <input
                class="form-radio bg-gray-900 border-transparent border-radius-lg text-indigo-500 h-6 w-6"
                type="radio"
                name="propertyType"
                value="house"
              />
              <span class="ml-2 text-sm text-white">House</span>
            </label>
            <label class="mt-3 sm:w-1/4 sm:px-2 flex items-center lg:px-0">
              <input
                class="form-radio bg-gray-900 border-transparent border-radius-lg text-indigo-500 h-6 w-6"
                type="radio"
                name="propertyType"
                value="apartment"
              />
              <span class="ml-2 text-sm text-white">Apartment</span>
            </label>
            <label class="mt-3 sm:w-1/4 sm:px-2 flex items-center lg:px-0">
              <input
                class="form-radio bg-gray-900 border-transparent border-radius-lg text-indigo-500 h-6 w-6"
                type="radio"
                name="propertyType"
                value="loft"
              />
              <span class="ml-2 text-sm text-white">Loft</span>
            </label>
            <label class="mt-3 sm:w-1/4 sm:px-2 flex items-center lg:px-0">
              <input
                class="form-radio bg-gray-900 border-transparent border-radius-lg text-indigo-500 h-6 w-6"
                type="radio"
                name="propertyType"
                value="Townhouse"
              />
              <span class="ml-2 text-sm text-white">Townhouse</span>
            </label>
          </div>
        </div>
        <!-- ============================================= -->
        <div class="px-4 py-4 border-t border-gray-900 lg:w-1/3 lg:border-l xl:w-full">
          <span class="mt-1 text-sm font-semibold text-gray-500 block">Amenities</span>
          <div class="sm:flex sm:-mx-2 sm:flex-wrap">
            <label class="mt-3 sm:w-1/4 sm:px-2 flex items-center lg:w-1/2 xl:w-full">
              <input
                class="form-checkbox bg-gray-900 border-transparent text-indigo-500 h-6 w-6"
                type="checkbox"
                name="balcony"
              />
              <span class="ml-2 text-sm text-white">Balcony</span>
            </label>
            <label class="mt-3 sm:w-1/4 sm:px-2 flex items-center lg:w-1/2 xl:w-full">
              <input
                class="form-checkbox bg-gray-900 border-transparent text-indigo-500 h-6 w-6"
                type="checkbox"
                name="airConditioning"
              />
              <span class="ml-2 text-sm text-white">Air conditioning</span>
            </label>
            <label class="mt-3 sm:w-1/4 sm:px-2 flex items-center lg:w-1/2 xl:w-full">
              <input
                class="form-checkbox bg-gray-900 border-transparent text-indigo-500 h-6 w-6"
                type="checkbox"
                name="pool"
              />
              <span class="ml-2 text-sm text-white">Pool</span>
            </label>
            <label class="mt-3 sm:w-1/4 sm:px-2 flex items-center lg:w-1/2 xl:w-full">
              <input
                class="form-checkbox bg-gray-900 border-transparent text-indigo-500 h-6 w-6"
                type="checkbox"
                name="beach"
              />
              <span class="ml-2 text-sm text-white">Beach</span>
            </label>
            <label class="mt-3 sm:w-1/4 sm:px-2 flex items-center lg:w-1/2 xl:w-full">
              <input
                class="form-checkbox bg-gray-900 border-transparent text-indigo-500 h-6 w-6"
                type="checkbox"
                name="petFriendly"
              />
              <span class="ml-2 text-sm text-white">Pet friendly</span>
            </label>
            <label class="mt-3 sm:w-1/4 sm:px-2 flex items-center lg:w-1/2 xl:w-full">
              <input
                class="form-checkbox bg-gray-900 border-transparent text-indigo-500 h-6 w-6"
                type="checkbox"
                name="kidFriendly"
              />
              <span class="ml-2 text-sm text-white">Kid friendly</span>
            </label>
            <label class="mt-3 sm:w-1/4 sm:px-2 flex items-center lg:w-1/2 xl:w-full">
              <input
                class="form-checkbox bg-gray-900 border-transparent text-indigo-500 h-6 w-6"
                type="checkbox"
                name="parking"
              />
              <span class="ml-2 text-sm text-white">Parking</span>
            </label>
          </div>
        </div>
      </div>
      <!-- ============================================= -->
      <div class="bg-gray-900 px-4 py-4 sm:text-right">
        <button
          class="block w-full sm:w-auto sm:inline-block bg-indigo-500 hover:bg-indigo-400 focus:outline-none text-white font-semibold px-4 py-2 rounded-lg xl:block xl:w-full"
        >Update Results</button>
      </div>
    </form>
    <!-- =============================================== -->
  </section>
</template>

<script>
export default {
  props: [],
  data() {
    return {
      isOpen: true
    };
  },
  methods: {
    toggle() {
      this.isOpen = !this.isOpen;
    }
  }
};
</script>
