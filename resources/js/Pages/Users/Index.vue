<template>
    <layout>
        <div class="my-3">
            <a href="/users/create" class=" btn btn-primary btn-lg">New User</a>
        </div>
        <table class="table table-striped">
            <thead>
                <tr>
                    <th scope="col">#</th>
                    <th scope="col">Name</th>
                    <th scope="col">Email</th>
                    <th scope="col">Actions</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="user in users" :key="user.id">
                    <th scope="row" v-text="user.id"></th>
                    <td v-text="user.name"></td>
                    <td v-text="user.email"></td>
                    <td>
                        <inertia-link
                            class="mx-1 btn btn-outline-info btn-md"
                            :href="`/users/${user.id}/edit`"
                        >
                            Edit
                        </inertia-link>
                        <a class="mx-1 btn btn-outline-danger btn-md" href="#"
                            >Delete</a
                        >
                    </td>
                </tr>
            </tbody>
        </table>
    </layout>
</template>

<script>
import Layout from "../Shared/Layout";

export default {
    components: {
        Layout
    },
    props: ["users"]
};
</script>
