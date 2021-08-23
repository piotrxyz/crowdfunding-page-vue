<template>
  <section class="section">
    <img alt="logo" src="../assets/logo-mastercraft.svg" />
    <MainPage msg="Mastercraft Bamboo Monitor Riser" />
    <div class="settings__group" v-for="select in selects" :key="select">
      <label class="settings__label">{{ select.name }}</label>
      <select class="settings__select" @change="addGroupToSelectedGroups">
        <option style="display: none"></option>
        <option
          v-for="option of select.options"
          :key="option"
          class="settings__option"
        >
          {{ option }}
        </option>
      </select>
    </div>
    <span class="selected__groups" v-for="group of selectedGroups" :key="group">
      {{ group }}
      <button @click="removeGroupFromSelectedGroups(group)">x</button>
    </span>
  </section>
</template>

<script>
// @ is an alias to /src
import MainPage from '@/components/MainPage.vue';
import keys from '@/constants/keys';

export default {
  name: 'Home',
  data() {
    return {
      selects: keys.selects,
      options: keys.selects[0].options,
      selectedGroups: keys.selectedGroups,
    };
  },
  components: {
    MainPage,
  },
  methods: {
    incrementCount() {
      this.count++;
    },
    addGroupToSelectedGroups(e) {
      console.log(e.target.value);
      let value = e.target.value;
      const selectedGroups = this.selectedGroups;
      if (selectedGroups.indexOf(value) === -1) {
        // check if elements exists in the array
        selectedGroups.unshift(value); // add group to selected groups if there is no such group
        this.options = this.options.filter((option) => option !== value); // remove selected group from select options
      }
    },
    removeGroupFromSelectedGroups(group) {
      this.selectedGroups = this.selectedGroups.filter(
        (option) => option !== group
      );
      this.options.unshift(group);
    },
  },
};
</script>

<style lang="scss" scoped>
.tests {
  font-size: 2rem;
  padding: 50px;
}
.settings {
  &__group {
    padding: 30px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  &__select {
    margin: 30px;
    width: 300px;
  }
}
</style>
