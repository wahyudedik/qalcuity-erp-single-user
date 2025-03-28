<script>
import { Link, useForm } from '@inertiajs/inertia-vue3';
import AppLayout from '@/Layouts/AppLayout.vue';

export default {
    components: {
        AppLayout,
        Link
    },
    props: {
        permission: Object
    },
    setup(props) {
        const form = useForm({
            name: props.permission.name
        });

        return { form };
    },
    methods: {
        submit() {
            this.form.put(route('permissions.update', this.permission.id));
        }
    }
}
</script>

<template>
    <AppLayout title="Edit Permission">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Edit Permission</h2>
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
                                    id="name" type="text" placeholder="Permission Name">
                                <div v-if="form.errors.name" class="text-red-500 text-xs mt-1">{{ form.errors.name }}
                                </div>
                            </div>

                            <div class="flex items-center justify-between">
                                <button
                                    class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
                                    type="submit" :disabled="form.processing">
                                    Update
                                </button>
                                <Link :href="route('permissions.index')"
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
