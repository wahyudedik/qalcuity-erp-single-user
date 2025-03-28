<script>
import { Link } from '@inertiajs/vue3';
import AppLayout from '@/Layouts/AppLayout.vue';
import Pagination from '@/Components/Pagination.vue';
import { router } from '@inertiajs/vue3';

export default {
    components: {
        AppLayout,
        Link,
        Pagination
    },
    props: {
        roles: Object
    },
    methods: {
        deleteRole(role) {
            if (confirm(`Are you sure you want to delete the role "${role.name}"?`)) {
                router.delete(route('roles.destroy', role.id));
            }
        }
    }
}
</script>

<template>
    <AppLayout title="Roles">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Roles</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 bg-white border-b border-gray-200">
                        <div class="flex justify-between mb-6">
                            <div>
                                <Link :href="route('roles.create')" class="px-4 py-2 bg-gray-800 text-white rounded-md">
                                Create Role
                                </Link>
                            </div>
                        </div>

                        <table class="min-w-full divide-y divide-gray-200">
                            <thead class="bg-gray-50">
                                <tr>
                                    <th
                                        class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                                        Name</th>
                                    <th
                                        class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                                        Permissions</th>
                                    <th
                                        class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                                        Actions</th>
                                </tr>
                            </thead>
                            <tbody class="bg-white divide-y divide-gray-200">
                                <tr v-for="role in roles.data" :key="role.id">
                                    <td class="px-6 py-4 whitespace-nowrap">{{ role.name }}</td>
                                    <td class="px-6 py-4">
                                        <span v-for="(permission, index) in role.permissions" :key="permission.id"
                                            class="inline-flex items-center px-2.5 py-0.5 rounded-full text-xs font-medium bg-green-100 text-green-800 mr-2 mb-1">
                                            {{ permission.name }}
                                        </span>
                                    </td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                                        <Link :href="route('roles.edit', role.id)"
                                            class="text-indigo-600 hover:text-indigo-900 mr-3">Edit</Link>
                                        <button @click="deleteRole(role)"
                                            class="text-red-600 hover:text-red-900">Delete</button>
                                    </td>
                                </tr>
                            </tbody>
                        </table>

                        <Pagination :links="roles.links" class="mt-6" />
                    </div>
                </div>
            </div>
        </div>
    </AppLayout>
</template>
