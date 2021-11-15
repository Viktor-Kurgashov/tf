<template>
  <table class="events-table app-table">
    <caption class="app-table__caption">События</caption>

    <tr class="app-table__row">
      <td class="events-table-date">Дата</td>
      <td class="events-table-event">Событие</td>
    </tr>

    <tr v-for="item of events" :key="item.event" class="app-table__row">
      <td class="events-table-date">{{ item.ctime }}</td>
      <td class="events-table-event">{{ item.event }}</td>
    </tr>
  </table>
</template>



<script>
export default {
  data () {
    return {
      events: []
    }
  },

  mounted () {
    const conn = new WebSocket('wss://test.relabs.ru/event');

    conn.onmessage = event => {
      const obj = JSON.parse(event.data), d = new Date(obj.ctime * 1000);

      obj.ctime =
        d.getDate().toString().padStart(2, 0) + '.' +
        (d.getMonth() + 1 + '').padStart(2, 0) + '.' +
        d.getFullYear() + ' ' +
        d.getHours().toString().padStart(2, 0) + ':' +
        d.getMinutes().toString().padStart(2, 0);

      this.events.push(obj);
    }
  }
}
</script>



<style>
.events-table-date,
.events-table-event {
  flex-basis: 50%;
}
</style>
