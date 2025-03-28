<script>
import { Link, useForm } from '@inertiajs/inertia-vue3';
import AppLayout from '@/Layouts/AppLayout.vue';

export default {
    components: {
        AppLayout,
        Link
    },
    props: {
        role: Object,
        permissions: Array
    },
    setup(props) {
        const form = useForm({
            name: props.role.name,
            permissions: props.role.permissions.map(permission => permission.id)
        });

        return { form };
    },
    methods: {
        submit() {
            this.form.put(route('roles.update', this.role.id));
        }
    }
}
</script>

<template>
    <AppLayout title="Edit Role">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Edit Role</h2>
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
                                    id="name" type="text" placeholder="Role Name">
                                <div v-if="form.errors.name" class="text-red-500 text-xs mt-1">{{ form.errors.name }}
                                </div>
                            </div>

                            <div class="mb-4">
                                <label class="block text-gray-700 text-sm font-bold mb-2">
                                    Permissions
                                </label>
                                <div class="mt-2 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
                                    <div v-for="permission in permissions" :key="permission.id"
                                        class="flex items-center">
                                        <input :id="`permission-${permission.id}`" type="checkbox"
                                            v-model="form.permissions" :value="permission.id"
                                            class="h-4 w-4 text-indigo-600 focus:ring-indigo-500 border-gray-300 rounded">
                                        <label :for="`permission-${permission.id}`"
                                            class="ml-2 block text-sm text-gray-900">
                                            {{ permission.name }}
                                        </label>
                                    </div>
                                </div>
                                <div v-if="form.errors.permissions" class="text-red-500 text-xs mt-1">{{
                                    form.errors.permissions
                                }}</div>
                            </div>

                            <div class="flex items-center justify-between">
                                <button
                                    class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
                                    type="submit" :disabled="form.processing">
                                    Update
                                </button>
                                <Link :href="route('roles.index')"
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
