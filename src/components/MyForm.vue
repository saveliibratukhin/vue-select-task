<template>
  <form>
    <MySelect @selected="citySelected" :options="cityOptions"/>
    <MySelect @selected="workshopSelected" :options="workshopOptions" />
    <MySelect @selected="employeeSelected" :options="employeeOptions"/>
    <MySelect @selected="brigadeSelected" :options="brigadeOptions" />
    <MySelect @selected="shiftSelected" :options="shiftOptions" />
  </form>
</template>

<script>
import MySelect from './MySelect.vue';
export default {
  data() {
    return {
      cityOptions: new Set(this.employees.map(e => e.city)),
      workshopOptions: new Set(this.employees.map(e => e.workshop)),
      employeeOptions: new Set(this.employees.map(e => e.employee)),
      brigadeOptions: new Set(this.employees.map(e => e.brigade)),
      shiftOptions: new Set(this.employees.map(e => e.shift)),
      selectedData: {
        city: '',
        workshop: '',
        employee: '',
        brigade: '',
        shift: ''
      }
    }
  },
  props: {
    employees: {
      type: Array,
      required: true
    }
  },
  methods: {
    citySelected(value) {
      const filteredArray = this.employees.filter(e => !value || e.city === value)
      this.workshopOptions = new Set(filteredArray.map(e => e.workshop))
      this.employeeOptions = new Set(filteredArray.map(e => e.employee))
      this.selectedData.city = value
      this.setCookie()
    },
    workshopSelected(value) {
      this.employeeOptions = new Set(this.employees.filter(e => !value || e.workshop === value).map(e => e.employee))
      this.selectedData.workshop = value
      this.setCookie()
    },
    employeeSelected(value) {
      this.selectedData.employee = value
      this.setCookie()
    },
    brigadeSelected(value) {
      this.selectedData.brigade = value
      this.setCookie()
    },
    shiftSelected(value) {
      this.selectedData.shift = value
      this.setCookie()
    },
    setCookie() {
      document.cookie = 'selected_values=' + JSON.stringify(this.selectedData)
    }
  },
  components: {
    MySelect
  }
}
</script>

<style scoped>

</style>
