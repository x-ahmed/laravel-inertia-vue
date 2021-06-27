<template>
    <layout>
        <div class="row justify-content-center">
            <form
                class="col-md-8 my-5"
                :action="`/users/${this.id}`"
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
                <button type="submit" class="btn btn-primary">
                    Update
                </button>
            </form>
        </div>
    </layout>
</template>

<script>
import Layout from "../Shared/Layout";

export default {
    props: {
        user: Object,
        errors: Object
    },
    components: {
        Layout
    },
    mounted(){
        const {id, name, email} = this.user
        this.form.name = name
        this.form.email = email
        this.id = id
    },
    data: () => {
        return {
            form: {
                name: '',
                email: '',
            },
            id: null
        };
    },
    methods: {
        submit() {
            this.$inertia.patch(`/users/${this.id}`, this.form);
        }
    }
};
</script>
