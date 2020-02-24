<template>
    <div class="container">
        <div class="row">
            <div class="col-md-12">
                <div class="card">
                    <div class="card-header with-border">
                        <h3 class="card-title mt-2">User List</h3>
                        <div class="card-tools pull-right">
                            <button class="btn btn-success mt-2" data-toggle="modal" data-target="#addUser">
                                <i class="fas fa-plus"></i> Add User
                            </button>                            
                        </div>
                    </div>
                    <!-- /.card-header -->
                    <div class="card-body table-responsive no-padding">
                        <table class="table table-bordered table-hover">
                            <tbody>
                                <tr>
                                    <th>Photo</th>
                                    <th>Name</th>
                                    <th>Email Address</th>
                                    <th>User Type</th>
                                    <th>Date Created</th>                                                       
                                    <th>Modify</th>
                                </tr>
                                <tr v-for="user in users" :key="user.id">
                                    <td>{{user.photo}}</td>
                                    <td>{{user.name}}</td>
                                    <td>{{user.email}}</td>
                                    <td>{{user.type | upperCase}}</td>
                                    <td>{{user.created_at | customDate}}</td>
                                    <td>
                                        <a href="#" title="Edit">
                                            <i class="fa fa-edit orange-icon"></i>
                                        </a>                    
                                        <a href="#" title="View Info">
                                            <i class="fa fa-eye orange-icon"></i>
                                        </a>
                                    </td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                    <!-- /.card-body -->
                </div>
                <!-- /.card -->
            </div>
            <!-- /.col-md-12 -->
        </div>
        <!-- /.row -->

        <!-- Modal -->
        <div class="modal fade" id="addUser" tabindex="-1" role="dialog" aria-labelledby="addUserTitle" aria-hidden="true">
            <div class="modal-dialog modal-dialog-centered" role="document">
                <div class="card modal-content">
                    <div class="card-header modal-header">
                        <h5 class="modal-title" id="addUserTitle">Create New User</h5>
                        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                            <span aria-hidden="true">&times;</span>
                        </button>
                    </div>
                    <form @submit.prevent="createUser">
                        <div class="modal-body">
                            <div class="form-group">
                                <label class="col-sm-6 control-label" for="date">Name</label>
                                <div class="col-sm-12">
                                    <input v-model="form.name" name="name" type="text" class="form-control" :class="{ 'is-invalid':form.errors.has('name')}">
                                    <has-error :form="form" field="name"></has-error>
                                </div>
                            </div>
                            <div class="form-group">
                                <label class="col-sm-6 control-label" for="date">Email</label>
                                <div class="col-sm-12">
                                    <input v-model="form.email" name="email" type="email" class="form-control" :class="{ 'is-invalid':form.errors.has('email')}">
                                    <has-error :form="form" field="email"></has-error>
                                </div>
                            </div>
                            <div class="form-group">
                                <label class="col-sm-6 control-label" for="date">Password</label>
                                <div class="col-sm-12">
                                    <input v-model="form.password" name="password" type="password" class="form-control" :class="{ 'is-invalid':form.errors.has('password')}">
                                    <has-error :form="form" field="password"></has-error>
                                </div>
                            </div>
                            <div class="form-group">
                                <label class="col-sm-6 control-label" for="date">User Type</label>
                                <div class="col-sm-12">
                                    <select v-model="form.type" name="type" class="form-control" :class="{ 'is-invalid':form.errors.has('type')}">
                                        <option value="" disabled="">Select User Type</option>
                                        <option value="admin">Administrator</option>
                                        <option value="user">Standard User</option>
                                    </select>
                                    <has-error :form="form" field="type"></has-error>
                                </div>
                            </div>                                      
                        </div>
                        <div class="modal-footer">
                            <button type="button" class="btn btn-danger" data-dismiss="modal">Close</button>
                            <button type="submit" class="btn btn-primary">Add User</button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
    <!-- /.container -->


</template>

<script>
    export default {
        data() {
            return {
                users: {},
                form: new Form({
                    name: '',
                    email: '',
                    password: '',
                    type: '',
                    photo: ''

                })
            }
        },
        methods: {
            loadUsers(){
                axios.get("api/user").then(({ data }) => (this.users = data.data));
            },

            createUser(){
                this.$Progress.start();
                this.form.post('api/user');
                $('#addUser').modal('hide');
                toast.fire({
                    icon: 'success',
                    title: 'User created successfully'
                });

                this.$Progress.finish();
                this.loadUsers();
            }
        },

        mounted() {
            this.loadUsers();
        }
    }
</script>
