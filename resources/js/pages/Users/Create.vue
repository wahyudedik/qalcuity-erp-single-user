<script>
import { Link, useForm } from '@inertiajs/vue3';
import AppLayout from '@/Layouts/AppLayout.vue';

export default {
    components: {
        AppLayout,
        Link
    },
    props: {
        roles: Array
    },
    setup() {
        const form = useForm({
            name: '',
            email: '',
            password: '',
            password_confirmation: '',
            roles: []
        });

        return { form };
    },
    methods: {
        submit() {
            this.form.post(route('users.store'));
        }
    }
}
</script>

<template>
    <AppLayout title="Create User">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Create User</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 bg-white border-b border-gray-200">
                        <form @submit.prevent="submit">
                            <div class="mb-4">
                                <label class="block text-gray-700 text-sm font-bold mb-2" for="name">
                                    Name
                                </label>
                                <input v-model="form.name"
                                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                                    id="name" type="text" placeholder="Name">
                                <div v-if="form.errors.name" class="text-red-500 text-xs mt-1">{{ form.errors.name }}
                                </div>
                            </div>

                            <div class="mb-4">
                                <label class="block text-gray-700 text-sm font-bold mb-2" for="email">
                                    Email
                                </label>
                                <input v-model="form.email"
                                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                                    id="email" type="email" placeholder="Email">
                                <div v-if="form.errors.email" class="text-red-500 text-xs mt-1">{{ form.errors.email }}
                                </div>
                            </div>

                            <div class="mb-4">
                                <label class="block text-gray-700 text-sm font-bold mb-2" for="password">
                                    Password
                                </label>
                                <input v-model="form.password"
                                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                                    id="password" type="password" placeholder="Password">
                                <div v-if="form.errors.password" class="text-red-500 text-xs mt-1">{{
                                    form.errors.password }}
                                </div>
                            </div>

                            <div class="mb-4">
                                <label class="block text-gray-700 text-sm font-bold mb-2" for="password_confirmation">
                                    Confirm Password
                                </label>
                                <input v-model="form.password_confirmation"
                                    class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                                    id="password_confirmation" type="password" placeholder="Confirm Password">
                            </div>

                            <div class="mb-4">
                                <label class="block text-gray-700 text-sm font-bold mb-2">
                                    Roles
                                </label>
                                <div class="mt-2">
                                    <div v-for="role in roles" :key="role.id" class="flex items-center mb-2">
                                        <input :id="`role-${role.id}`" type="checkbox" v-model="form.roles"
                                            :value="role.id"
                                            class="h-4 w-4 text-indigo-600 focus:ring-indigo-500 border-gray-300 rounded">
                                        <label :for="`role-${role.id}`" class="ml-2 block text-sm text-gray-900">
                                            {{ role.name }}
                                        </label>
                                    </div>
                                </div>
                                <div v-if="form.errors.roles" class="text-red-500 text-xs mt-1">{{ form.errors.roles }}
                                </div>
                            </div>

                            <div class="flex items-center justify-between">
                                <button
                                    class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
                                    type="submit" :disabled="form.processing">
                                    Create
                                </button>
                                <Link :href="route('users.index')"
                                    class="inline-block align-baseline font-bold text-sm text-blue-500 hover:text-blue-800">
                                Cancel
                                </Link>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </AppLayout>
</template>
