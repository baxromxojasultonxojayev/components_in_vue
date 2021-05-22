<template>
  <div>
    <the-header></the-header>
    <!-- <badge-list></badge-list>
    <user-info
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    ></user-info>
    <course-goal>
      <template v-slot="slotProps">
        <h2>{{ slotProps.item }}</h2>
        <p>{{ slotProps['another-prop'] }}</p>
      </template>
    </course-goal> -->
    <button @click="setSelectedComponents('active-goals')"> Active goals</button>
    <button @click="setSelectedComponents('manage-goals')">Manage Goals</button>

    <!-- <active-goals v-if="selectedComponent === 'active-goals'"></active-goals>
    <manage-goals v-if="selectedComponent !== 'active-goals'"></manage-goals> -->
    <keep-alive>
      <component :is="selectedComponent"></component>
    </keep-alive>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue'
// import BadgeList from './components/BadgeList.vue';
// import UserInfo from './components/UserInfo.vue';
// import CourseGoal from './components/CourseGoal'
import ActiveGoals from './components/ActiveGoals'
import ManageGoals from './components/ManageGoals'

export default {
  components: {
    TheHeader,
    ActiveGoals,
    ManageGoals
    // 'the-header': TheHeader
  },
  data() {
    return {
      selectedComponent: 'active-goals',
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
  methods: {
    setSelectedComponents(cmp){
      this.selectedComponent = cmp 
    }
  }
};
</script>

<style scoped>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>