<template>
    <form @submit.prevent="submit">
        <div class="grid items-end gap-6 mb-6 lg:grid-cols-2">
            <div class="relative z-0 w-full mb-6 group">
                <input
                    v-model="form.name"
                    type="text"
                    name="name"
                    id="name"
                    aria-describedby="outlined_success_help"
                    class="block px-2.5 pb-2.5 pt-4 w-full text-sm text-gray-900 bg-transparent rounded-lg border-1 border-green-600 appearance-none dark:text-white dark:border-green-500 dark:focus:border-green-500 focus:outline-none focus:ring-0 focus:border-green-600 peer"
                    :class="{
                        'focus:border-red-600 dark:focus:border-red-500':
                            errors.name,
                        'focus:border-blue-600 dark:focus:border-blue-500':
                            !errors.name,
                    }"
                    placeholder=" "
                />
                <p
                    v-if="errors.name"
                    class="absolute mt-2 text-xs text-red-600 dark:text-red-400"
                >
                    {{ errors.name }}
                </p>
                <label
                    for="name"
                    class="absolute text-sm text-green-600 dark:text-green-500 duration-300 transform -translate-y-4 scale-75 top-2 z-10 origin-[0] bg-white dark:bg-gray-800 px-2 peer-focus:px-2 peer-placeholder-shown:scale-100 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:top-1/2 peer-focus:top-2 peer-focus:scale-75 peer-focus:-translate-y-4 left-1"
                    :class="{
                        'peer-focus:text-red-600 peer-focus:dark:text-red-500':
                            errors.name,
                        'peer-focus:text-blue-600 peer-focus:dark:text-blue-500':
                            !errors.name,
                    }"
                    >Name</label
                >
            </div>
            <div class="relative z-0 w-full mb-6 group">
                <input
                    v-model="form.email"
                    type="email"
                    name="email"
                    class="block px-2.5 pb-2.5 pt-4 w-full text-sm text-gray-900 bg-transparent rounded-lg border-1 border-green-600 appearance-none dark:text-white dark:border-green-500 dark:focus:border-green-500 focus:outline-none focus:ring-0 focus:border-green-600 peer"
                    placeholder=" "
                    :class="{
                        'focus:border-red-600 dark:focus:border-red-500':
                            errors.email,
                        'focus:border-blue-600 dark:focus:border-blue-500':
                            !errors.email,
                    }"
                />
                <label
                    for="email"
                    class="absolute text-sm text-green-600 dark:text-green-500 duration-300 transform -translate-y-4 scale-75 top-2 z-10 origin-[0] bg-white dark:bg-gray-800 px-2 peer-focus:px-2 peer-placeholder-shown:scale-100 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:top-1/2 peer-focus:top-2 peer-focus:scale-75 peer-focus:-translate-y-4 left-1"
                    :class="{
                        'peer-focus:text-red-600 peer-focus:dark:text-red-500':
                            errors.email,
                        'peer-focus:text-blue-600 peer-focus:dark:text-blue-500':
                            !errors.email,
                    }"
                    >Email address</label
                >
                <p
                    v-if="errors.email"
                    class="absolute mt-2 text-xs text-red-600 dark:text-red-400"
                >
                    {{ errors.email }}
                </p>
            </div>
            <div class="relative z-0 w-full mb-6 group">
                <input
                    v-model="form.password"
                    type="password"
                    name="password"
                    id="password"
                    class="block px-2.5 pb-2.5 pt-4 w-full text-sm text-gray-900 bg-transparent rounded-lg border-1 border-green-600 appearance-none dark:text-white dark:border-green-500 dark:focus:border-green-500 focus:outline-none focus:ring-0 focus:border-green-600 peer"
                    placeholder=" "
                    :class="{
                        'focus:border-red-600 dark:focus:border-red-500':
                            errors.password,
                        'focus:border-blue-600 dark:focus:border-blue-500':
                            !errors.password,
                    }"
                />
                <label
                    for="password"
                    class="absolute text-sm text-green-600 dark:text-green-500 duration-300 transform -translate-y-4 scale-75 top-2 z-10 origin-[0] bg-white dark:bg-gray-800 px-2 peer-focus:px-2 peer-placeholder-shown:scale-100 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:top-1/2 peer-focus:top-2 peer-focus:scale-75 peer-focus:-translate-y-4 left-1"
                    :class="{
                        'peer-focus:text-red-600 peer-focus:dark:text-red-500':
                            errors.password,
                        'peer-focus:text-blue-600 peer-focus:dark:text-blue-500':
                            !errors.password,
                    }"
                    >Password</label
                >
                <p
                    v-if="errors.password"
                    class="absolute mt-2 text-xs text-red-600 dark:text-red-400"
                >
                    {{ errors.password }}
                </p>
            </div>
            <div class="relative z-0 w-full mb-6 group">
                <input
                    v-model="form.password_confirmation"
                    type="password"
                    name="pasword_confirmation"
                    id="pasword_confirmation"
                    class="block px-2.5 pb-2.5 pt-4 w-full text-sm text-gray-900 bg-transparent rounded-lg border-1 border-green-600 appearance-none dark:text-white dark:border-green-500 dark:focus:border-green-500 focus:outline-none focus:ring-0 focus:border-green-600 peer"
                    placeholder=" "
                    :class="{
                        'focus:border-red-600 dark:focus:border-red-500':
                            errors.password_confirmation,
                        'focus:border-blue-600 dark:focus:border-blue-500':
                            !errors.password_confirmation,
                    }"
                />
                <label
                    for="pasword_confirmation"
                    class="absolute text-sm text-green-600 dark:text-green-500 duration-300 transform -translate-y-4 scale-75 top-2 z-10 origin-[0] bg-white dark:bg-gray-800 px-2 peer-focus:px-2 peer-placeholder-shown:scale-100 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:top-1/2 peer-focus:top-2 peer-focus:scale-75 peer-focus:-translate-y-4 left-1"
                    :class="{
                        'peer-focus:text-red-600 peer-focus:dark:text-red-500':
                            errors.password_confirmation,
                        'peer-focus:text-blue-600 peer-focus:dark:text-blue-500':
                            !errors.password_confirmation,
                    }"
                    >Password Confirmation</label
                >
                <p
                    v-if="errors.password_confirmation"
                    class="absolute mt-2 text-xs text-red-600 dark:text-red-400"
                >
                    {{ errors.password_confirmation }}
                </p>
            </div>
        </div>
        <div class="text-right">
            <Link
                :href="route('user.index')"
                class="p-2 mr-3 text-sm text-white transition-colors bg-gray-500 rounded-md hover:bg-gray-800 hover:transition-shadow"
            >
                <font-awesome-icon :icon="['fas', 'arrow-left']" />
                Cancel
            </Link>
            <button
                type="submit"
                class="p-2 text-sm text-white transition-colors bg-green-500 rounded-md hover:bg-green-800 hover:transition-shadow"
            >
                <font-awesome-icon :icon="['fas', 'plus']" />
                {{ isEdit ? "Update" : "Create" }}
            </button>
        </div>
    </form>
</template>
<script>
import { Inertia } from "@inertiajs/inertia";
export default {
    name: "FormUser",
    props: {
        errors: {
            type: Object,
            default: () => ({}),
        },
        isEdit: {
            type: Boolean,
            default: false,
        },
        customer: {
            type: Object,
            default: () => ({}),
        },
    },
    data() {
        return {
            form: {
                id: this.customer.id ? this.customer.id : null,
                name: this.customer.name ? this.customer.name : "",
                email: this.customer.email ? this.customer.email : "",
                password: "",
                password_confirmation: "",
            },
        };
    },
    methods: {
        submit() {
            if (this.isEdit) {
                Inertia.put(route("user.update", this.form.id), this.form);
            } else {
                Inertia.post(route("user.store"), this.form);
            }
        },
    },
};
</script>
