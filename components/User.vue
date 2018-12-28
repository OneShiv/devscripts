<template>
    <div class="component">
        <h1>The User Component</h1>
        <p>I'm an awesome User!</p>
        <p>{{ firstName }}</p>
         <p>{{ age }}</p>
        <button @click="changeName">Click to change Name</button>
        
        <hr>
        <div class="row">
            <div class="col-xs-12 col-sm-6">
                <app-user-detail 
                :name="firstName" 
                :usrAge="age"
                @nameReset="firstName=$event"
                :resetFn="resetName"
                ></app-user-detail>
            </div>
            <div class="col-xs-12 col-sm-6">
                <app-user-edit :userAge="age"></app-user-edit>
            </div>
        </div>
    </div>
</template>

<script>
    import UserDetail from './UserDetail.vue';
    import UserEdit from './UserEdit.vue';
  
    export default {
        components: {
            appUserDetail: UserDetail,
            appUserEdit: UserEdit
        },
        data:function(){
            return {
                firstName:'Shivshankar',
                age:27
            }
        },
        methods:{
            changeName(){
                this.firstName='Pradnya';
            },
            resetName(){
                this.firstName='abra ka dabra';
            }    
        }
    }
</script>

<style scoped>
    div {
        background-color: lightblue;
    }
</style>
