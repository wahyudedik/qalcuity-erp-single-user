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
        permissions: Object
    },
    methods: {
        deletePermission(permission) {
            if (confirm(`Are you sure you want to delete the permission "${permission.name}"?`)) {
                router.delete(route('permissions.destroy', permission.id));
            }
        }
    }
}
</script>

<template>
    <AppLayout title="Permissions">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Permissions</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 bg-white border-b border-gray-200">
                        <div class="flex justify-between mb-6">
                            <div>
                                <Link :href="route('permissions.create')"
                                    class="px-4 py-2 bg-gray-800 text-white rounded-md">
                                Create Permission
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
                                        Actions</th>
                                </tr>
                            </thead>
                            <tbody class="bg-white divide-y divide-gray-200">
                                <tr v-for="permission in permissions.data" :key="permission.id">
                                    <td class="px-6 py-4 whitespace-nowrap">{{ permission.name }}</td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                                        <Link :href="route('permissions.edit', permission.id)"
                                            class="text-indigo-600 hover:text-indigo-900 mr-3">Edit</Link>
                                        <button @click="deletePermission(permission)"
                                            class="text-red-600 hover:text-red-900">Delete</button>
                                    </td>
                                </tr>
                            </tbody>
                        </table>

                        <Pagination :links="permissions.links" class="mt-6" />
                    </div>
                </div>
            </div>
        </div>
    </AppLayout>
</template>
