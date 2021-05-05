<template>
  <div>
    <h1>Events</h1>
    <ul v-for="event in events" :key="event.id">
      <li>
        <nuxt-link
          :to="{ name: 'category', params: { category: event.title } }"
          >{{ event.title }}</nuxt-link
        >
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      events: [
        { id: 1, title: 'hot' },
        { id: 2, title: 'item' },
        { id: 3, title: 'culture' },
        { id: 4, title: 'travel' },
      ],
    }
  },
  head() {
    return {
      title: 'Event Listing',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content:
            'Where you can find all the events taking place in your neighborhood',
        },
      ],
    }
  },
}
</script>

<style></style>
