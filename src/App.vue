<template>
  <MyForm :employees="employees"/>
</template>

<script>
import MyForm from './components/MyForm.vue'

export default {
  data() {
    return {
      employees: [
        {
            city: 'EKB',
            workshop: 'EKB-1',
            employee: 'Oleg',
            brigade: 1,
            shift: 1
        },
        {
            city: 'EKB',
            workshop: 'EKB-2',
            employee: 'Sergey',
            brigade: 1,
            shift: 1
        },
        {
            city: 'EKB',
            workshop: 'EKB-2',
            employee: 'Artem',
            brigade: 2,
            shift: 3
        },
        {
            city: 'MSK',
            workshop: 'MSK-1',
            employee: 'Sergey',
            brigade: 10,
            shift: 3
        },
        {
            city: 'MSK',
            workshop: 'MSK-2',
            employee: 'Vladislav',
            brigade: 10,
            shift: 3
        },
        {
            city: 'MSK',
            workshop: 'MSK-2',
            employee: 'Alexander',
            brigade: 5,
            shift: 2
        },
        {
            city: 'MSK',
            workshop: 'MSK-2',
            employee: 'Vladimir',
            brigade: 4,
            shift: 1
        },
        {
            city: 'MSK',
            workshop: 'MSK-2',
            employee: 'Andrey',
            brigade: 4,
            shift: 1
        },
        {
            city: 'MSK',
            workshop: 'MSK-3',
            employee: 'Mihail',
            brigade: 1,
            shift: 3
        },
      ]
    }
  },
  components: {
    MyForm: MyForm
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
