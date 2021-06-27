<template>
    <layout>
        <div class="row justify-content-center">
            <form
                class="col-md-8 my-5"
                action="/users"
                method="POST"
                @click.prevent="submit"
            >
                <div class="form-group">
                    <label for="name">Name</label>
                    <input
                        type="text"
                        class="form-control"
                        id="name"
                        placeholder="your name"
                        v-model="form.name"
                    />
                    <div v-if="errors.name">
                        <span class="text-danger">{{ errors.name }}</span>
                    </div>
                </div>
                <div class="form-group">
                    <label for="email">Email address</label>
                    <input
                        type="email"
                        class="form-control"
                        id="email"
                        placeholder="valid email address"
                        v-model="form.email"
                    />
                    <div v-if="errors.email">
                        <span class="text-danger">{{ errors.email }}</span>
                    </div>
                </div>
                <div class="form-group">
                    <label for="password">Password</label>
                    <input
                        type="password"
                        class="form-control"
                        id="password"
                        placeholder="secured password"
                        v-model="form.password"
                    />
                    <div v-if="errors.password">
                        <span class="text-danger">{{ errors.password }}</span>
                    </div>
                </div>
                <button type="submit" class="btn btn-primary">
                    Create
                </button>
            </form>
        </div>
    </layout>
</template>

<script>
import Layout from "../Shared/Layout";

export default {
    props: {
        errors: Object
    },
    components: {
        Layout
    },
    data: () => {
        return {
            form: {
                name: "",
                email: "",
                password: ""
            }
        };
    },
    methods: {
        submit() {
            this.$inertia.post("/users", this.form);
        }
    }
};
</script>
