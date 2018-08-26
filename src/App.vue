<template>
  <div id="app">
    <div class="container">
      <h1>Vue Generic Table</h1>
      Here's an example of what I did @ Yoopies during my internship.
      You can play with the given options such as pagination
      or the total displaying items with limit.
      <div class="form-group">
        <b-form inline>
          <b-form-checkbox
            v-model="isPaginated"
            type="checkbox"
          >
            Pagination ?
          </b-form-checkbox>
          <b-form-input
            v-model.number="limit"
            class="custom-control-inline"
            type="range"
            min="1"
            max="10"
          /> Limit: {{ limit }}
        </b-form>
      </div>
      <GenericTable
        :columns="columns"
        :data="data"
        :init-limit="limit"
        :is-paginated="isPaginated"
      />
    </div>
  </div>
</template>

<script>
import GenericTable from './components/genericTable.vue';

export default {
  name: 'App',
  components: {
    GenericTable,
  },
  data() {
    return {
      isPaginated: false,
      limit: 2,
      columns: ['name', 'country', 'birthdate', 'visited countries'],
      data: [
        {
          name: 'Franck',
          country: 'France',
          birthdate: '1994-03-18',
          'visited countries': 4,
        },
        {
          name: 'Caroline',
          country: 'France',
          birthdate: '1993-07-01',
          'visited countries': 6,
        },
        {
          name: 'Paul',
          country: 'France',
          birthdate: '1990-09-03',
          'visited countries': 2,
        },
        {
          name: 'Peter',
          country: 'UK',
          birthdate: '1996-02-20',
          'visited countries': 1,
        },
        {
          name: 'Gabriel',
          country: 'UK',
          birthdate: '2000-07-08',
          'visited countries': 10,
        },
        {
          name: 'Matheus',
          country: 'UK',
          birthdate: '2003-10-10',
          'visited countries': 5,
        },
        {
          name: 'Gabriel',
          country: 'Germany',
          birthdate: '1996-02-20',
          'visited countries': 1,
        },
        {
          name: 'Naomi',
          country: 'Germany',
          birthdate: '2000-07-08',
          'visited countries': 10,
        },
        {
          name: 'Marwa',
          country: 'Germany',
          birthdate: '2003-10-10',
          'visited countries': 5,
        },
      ],
    };
  },
};
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
