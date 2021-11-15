<template>
  <div class="users-list">
    <Loader v-if="pending" class="users-list-loader" />

    <table class="app-table users-table">
      <caption class="app-table__caption">Пользователи</caption>

      <tr class="app-table__row">
        <td class="users-table-id">ID</td>
        <td class="users-table-name">Имя</td>
        <td class="users-table-role">Роль</td>
        <td class="users-table-date">Дата создания</td>
        <button class="users-table__delete-btn"></button>
      </tr>


      <tr class="app-table__row"
        v-for="user of pageItems.filter(item => (!item.hidden))"
        :key="user.id"
      >  
        <td class="users-table-id">{{ user.id }}</td>
        <td class="users-table-name">{{ user.name }}</td>
        <td class="users-table-role">{{ user.role }}</td>
        <td class="users-table-date">{{ user.ctime }}</td>

        <button class="users-table__delete-btn" @click="deleteUser($event)">
          <img class="users-table__btn-icon" src="@/assets/x.svg">
        </button>
      </tr>  
    </table>


    <router-link
      class="pagination-link"
      v-for="link of links"
      :key="link.route"
      :to="link.route"
    >
      {{ link.title }}
    </router-link>

  </div>
</template>



<script>
import Loader from '@/components/Loader.vue'

export default {
  components: { Loader },

  created() {
    this.getUsers('https://test.relabs.ru/api/users/list')
  },

  data () {
    return {
      users: [],
      links: [],
      pending: true
    }
  },

  computed: {
    pageItems () {
      const page = (!this.$route.params.num) ? '1' : this.$route.params.num;

      return this.users.slice(page * 5 - 5, page * 5);
    }
  },


  methods: {
    async getUsers (path) {
      await fetch(path)
        .then(res => res.json())
        .then(obj => {
          obj.items
            .map(item => {
              item.hidden = false;

              const d = new Date(item.ctime * 1000);

              item.ctime =
                d.getDate().toString().padStart(2, 0) + '.' +
                (d.getMonth() + 1 + '').padStart(2, 0) + '.' +
                d.getFullYear() + ' ' +
                d.getHours().toString().padStart(2, 0) + ':' +
                d.getMinutes().toString().padStart(2, 0);

              return item;
            })
            .forEach(item => this.users.push(item));


          this.links.push(
            (obj.page == 1) ?
            { route: '/', title: '1' } :
            { route: '/' + obj.page, title: obj.page }
          );


          if (obj.offset + obj.limit < obj.total) {
            this.getUsers(
              path.replace(
                /(\?offset=\d+)?$/,
                '?offset=' + (obj.offset + obj.limit)
              )
            );
          }
          else {
            setTimeout(() => this.pending = false, 500)
          }

        })
    },


    deleteUser (event) {
      const tableItemId = event.currentTarget.parentElement.firstElementChild.textContent;

      this.users[this.users.findIndex(item => item.id == tableItemId)].hidden = true;
    }
  }
}
</script>



<style>
.users-list {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-content: space-between;
  position: relative;
  min-height: 440px;
}
.users-list-loader {
  height: 330px;
  top: 110px;
}
.users-table {
  flex-basis: 100%;
}



.users-table-id {
  flex-basis: 10%;
}
.users-table-name {
  flex-basis: 25%;
}
.users-table-role {
  flex-basis: 20%;
}
.users-table-date {
  flex-basis: 40%;
}



.users-table__delete-btn {
  flex-basis: 5%;
  padding-top: 2px;
  font-size: 0;
}
.users-table__btn-icon {
  width: auto;
  height: 27px;
}



.pagination-link {
  background: whitesmoke;
  border-radius: 8px;
  text-align: center;
  width: 40px;
  height: 40px;
  line-height: 41px;
  margin-left: 10px;
}
.pagination-link:first-of-type {
  margin-left: 0;
}

.pagination-link.router-link-exact-active {
  background: dodgerblue;
  color: white;
}

</style>