<template>
  <div>
    <h1>Events</h1>
    <EventCard
      v-for="(event, index) in events"
      :key="event.id"
      :event="event"
      :data-index="index"
    />
  </div>
</template>

<script>
import EventCard from '@/components/EventCard.vue'

export default {
  components: {
    EventCard,
  },
  asyncData({ $axios, error }) {
    return $axios
      .get('http://localhost:3000/events')
      .then((response) => {
        return {
          events: response.data,
        }
      })
      .catch((e) => {
        error({
          statusCode: 503,
          message: 'Unable to fetch events at this time, please try again',
        })
      })
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
