<template>
    <div class="container">
        <table class="table table-bordered">
            <tr align="center">
                <th>#</th>
                <th>Name</th>
                <th>Email</th>
            </tr>

            <tr align="center" v-for="user in users">
                <th>{{user.id}}</th>
                <td>{{user.name}}</td>
                <td>{{user.email}}</td>
            </tr>

        </table>
    </div>
</template>

<script>
    export default {
        mounted() {
            this.show_data()
        },
        methods:{
            show_data(){
                axios.get('api/users').then(response=>{
                    this.users = response.data;
                })
            }
        },
        data(){
            return{
                users:[],
                user:{
                    id:0,
                    name:'',
                    email:''
                }
            }
        }
    }
</script>
