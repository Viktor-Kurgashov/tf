<template>
  <div class="home-page">
    <UsersList />
    <EventsTable />
  </div>
</template>



<script>
import UsersList from '@/components/UsersList.vue'
import EventsTable from '@/components/EventsTable.vue'

export default {
  components: {
    UsersList,
    EventsTable    
  },
}
</script>



<style>
.home-page {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
  align-items: flex-start;
}
.users-list {
  flex-basis: 53%;
}
.events-table {
  flex-basis: 43%;
}


@media screen and (max-width: 768px) {
  .users-list {
    flex-basis: 100%;
  }
  .events-table {
    flex-basis: 100%;
    margin-top: 40px;
  }
}

</style>
