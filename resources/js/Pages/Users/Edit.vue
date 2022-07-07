<template>
    <AppLayout title="Edit User">
        <template #header>
            <h2 class="text-xl font-semibold leading-tight text-gray-800">
                Edit User
            </h2>
        </template>
        <div class="py-12">
            <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
                <div class="overflow-hidden bg-white shadow-xl sm:rounded-lg">
                    <div
                        class="relative p-6 overflow-x-auto shadow-md sm:rounded-lg"
                    >
                        <FormUser
                            :errors="errors"
                            :isEdit="true"
                            :customer="customer"
                        />
                    </div>
                </div>
            </div>
        </div>
    </AppLayout>
</template>
<script>
import AppLayout from "@/Layouts/AppLayout.vue";
import FormUser from "./Form.vue";
export default {
    props: {
        errors: {
            type: Object,
            default: () => ({}),
        },
        customer: {
            type: Object,
            default: () => ({}),
        },
    },
    components: {
        AppLayout,
        FormUser,
    },
};
</script>
