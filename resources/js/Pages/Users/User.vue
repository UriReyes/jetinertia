<template>
    <AppLayout title="Users">
        <template #header>
            <h2 class="text-xl font-semibold leading-tight text-gray-800">
                Users
            </h2>
        </template>
        <div class="py-12">
            <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
                <div class="overflow-hidden bg-white shadow-xl sm:rounded-lg">
                    <div
                        class="relative p-6 overflow-x-auto shadow-md sm:rounded-lg"
                    >
                        <div class="mb-4 text-right">
                            <Link
                                :href="route('user.create')"
                                class="p-2 text-sm text-white transition-colors bg-blue-500 rounded-md hover:bg-blue-800 hover:transition-shadow"
                            >
                                <font-awesome-icon
                                    :icon="['fas', 'plus-circle']"
                                />
                                Create
                            </Link>
                        </div>
                        <table class="w-full text-sm text-left text-gray-500">
                            <thead
                                class="text-xs text-gray-700 uppercase bg-gray-50"
                            >
                                <tr>
                                    <th scope="col" class="px-6 py-3">ID</th>
                                    <th scope="col" class="px-6 py-3">Name</th>
                                    <th scope="col" class="px-6 py-3">Email</th>
                                    <th scope="col" class="px-6 py-3">
                                        Actions
                                    </th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr
                                    class="bg-white border-b hover:bg-gray-50"
                                    v-for="user in users"
                                    :key="user.id"
                                >
                                    <td
                                        scope="row"
                                        class="px-6 py-4 font-medium text-gray-900"
                                    >
                                        {{ user.id }}
                                    </td>
                                    <td class="px-6 py-4">{{ user.name }}</td>
                                    <td class="px-6 py-4">{{ user.email }}</td>
                                    <td class="px-6 py-4 text-right">
                                        <a
                                            href="#"
                                            class="font-medium text-blue-600 dark:text-blue-500 hover:underline"
                                            >Edit</a
                                        >
                                    </td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </AppLayout>
</template>

<script>
import AppLayout from "@/Layouts/AppLayout.vue";
export default {
    props: ["users"],
    components: {
        AppLayout,
    },
};
</script>

<style></style>
