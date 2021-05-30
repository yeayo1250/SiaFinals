<template>

    <div class="container">
        
        <h1 style="background-color:MediumSeaGreen;">LIST OF ENROLLEES</h1>
        <table class="table table-dark table-hover">
        <thead>
            <tr>
            <th scope="col">ID #</th>
            <th scope="col">FullName</th>
            <th scope="col">Email</th>
            <th scope="col">Address</th>
            <th scope="col">PhoneNumber</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="user in users" v-bind:key="user.id">
            <th scope="row">{{user.id}}</th>
            <td>{{user.name}}</td>
            <td>{{user.email}}</td>
            <td>{{user.address.city}}</td>
            <td>{{user.phone}}</td>
            </tr>
            </tbody>
                </table>
                </div>
</template>

<script>
    import axios from 'axios';

    export default {
        name: 'Users',
        data() {
            return {
                users: null,
            };
        },
        created: function() {
            axios
            .get('https://jsonplaceholder.typicode.com/users')
            .then(res => {
                this.users = res.data;
            })
        }
    }
</script>

<style></style>