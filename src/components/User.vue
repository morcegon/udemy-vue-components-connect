<template>
    <div class="component">
        <h1>The User Component</h1>
        <p>I'm an awesome User!</p>
        <button @click="changeName">Change my Name</button>
        <p>Name is {{ name }}</p>
        <hr>
        <div class="row">
            <div class="col-xs-12 col-sm-6">
                <app-user-detail
                  @nameWasReset="name=$event"
                  :myName="name"
                  :userAge="age"                  
                  :resetFn="resetName"></app-user-detail>
            </div>
            <div class="col-xs-12 col-sm-6">
                <app-user-edit
                  @ageWasChanged="age=$event"
                  :userAge="age"></app-user-edit>
            </div>
        </div>
    </div>
</template>

<script>
  import UserDetail from './UserDetail.vue';
  import UserEdit from './UserEdit.vue';

  export default {
    data: () => {
      return {
        name: 'Renan',
        age: 32
      }
    },
    methods: {
      changeName() {
        this.name = 'Bruna'
      },
      resetName() {
        this.name = "Renan"
      }
    },
    components: {
      appUserDetail: UserDetail,
      appUserEdit: UserEdit
    }
  }
</script>

<style scoped>
    div {
        background-color: lightblue;
    }
</style>
