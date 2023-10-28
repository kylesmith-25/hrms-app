<template>
    <div class="w-full h-screen bg-slate-100 background1">

        <div class="z-0 relative ">
            <div class="z-10 relative ">
                <div class="h-[25x] w-full bg-red-500 fixed">
                    <div>
                        <div class="flex">
                            <div>
                                <a :href="'/'">
                                    <p class="w-[250px] px-10 font-semibold text-slate-50 text-xl py-2 cursor-pointer">
                                        HRMS CENTRAL
                                    </p>
                                </a>
                            </div>
                            <nav class="flex h-full text-md text-slate-50">
                                <ul class="py-2.5 px-7 cursor-pointer hover:bg-red-600">
                                    <p class="hover:scale-105">
                                        About
                                    </p>
                                </ul>
                                <ul class="py-2.5 px-7 cursor-pointer hover:bg-red-600">
                                    <p class="hover:scale-105">
                                        Guide
                                    </p>
                                </ul>
                            </nav>
                            <div class="py-2 px-10 text-slate-50 text-lg w-full flex justify-end ">
                                <UserCircleIcon class="mx-5 h-6 w-6 hover:scale-105" />
                                user
                            </div>
                        </div>
                    </div>
                </div>
                <div class="z-20 absolute top-10 h-full w-full">
                    <div class="grid grid-cols-2">
                        <div class="cols-span-1">
                            <div class="h-full flex items-center justify-center">
                                <div class="cursor-default">
                                    <div class="text-red-600 text-6xl font-bold">
                                        Human Resources
                                    </div>
                                    <div class="flex w-full justify-between text-lg font-semibold">

                                        <div class="px-2 hover:scale-110">
                                            Payslips
                                        </div>
                                        <div class="px-2 hover:scale-110">
                                            JobLetters
                                        </div>
                                        <div class="px-2 hover:scale-110">
                                            Taxes
                                        </div>
                                        <div class="px-2 hover:scale-110">
                                            Time Off
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div class="cols-span-1">
                            <div class="h-full flex items-center w-full justify-end">
                                <div class="mt-20 mr-20 bg-red-500 h-[600px] w-[400px] rounded-md">
                                    <div class="h-full">
                                        <div class="h-[475px]">

                                            <div class="h-[400px]" v-show="!creatingAccount && !loggingIn">

                                                <div class="hover:scale-110">
                                                    <div
                                                        class="z-20 text-slate-50 text-3xl font-bold w-full flex justify-center pt-20 cursor-default">
                                                        Welcome
                                                    </div>
                                                    <div class="mt-20 w-full flex justify-center">

                                                        <div class="custom-bounce-pause-bounce w-full flex justify-center">

                                                            <div class="z-30 absolute flex ">
                                                                <div class="mr-[65px]">
                                                                    <div
                                                                        class="bg-amber-950 h-[60px] w-[30px] rounded-full">

                                                                    </div>
                                                                </div>
                                                                <div class="">
                                                                    <div
                                                                        class="bg-amber-950 h-[60px] w-[30px] rounded-full">

                                                                    </div>
                                                                </div>
                                                            </div>
                                                            <div class="z-40 absolute flex mt-[40px]">
                                                                <div class="mr-[14px]">
                                                                    <div class=" bg-black h-[15px] w-[15px] rounded-full">

                                                                    </div>
                                                                </div>
                                                                <div class="">
                                                                    <div class=" bg-black h-[15px] w-[15px] rounded-full ">

                                                                    </div>
                                                                </div>
                                                            </div>
                                                            <div
                                                                class=" h-[120px] w-[105px] rounded-full bg-white flex-col justify-center">
                                                                <div
                                                                    class="mt-[35px] ml-[28px] bg-amber-900 h-[30px] w-[20px] rounded-full">

                                                                </div>

                                                                <div class="w-full flex-col justify-center">
                                                                    <div class="w-full mt-3">
                                                                        <div class="w-full flex justify-center">
                                                                            <p
                                                                                class="h-5 w-5 border-2 border-black bg-black rounded-full ">
                                                                            </p>
                                                                        </div>
                                                                        <div class="w-full flex justify-center">
                                                                            <div
                                                                                class="border-r-4 border-black h-1 ">

                                                                            </div>
                                                                        </div>
                                                                        <p
                                                                            class="pr-6 rotate-90 text-4xl font-bold w-full flex justify-center">
                                                                            )
                                                                        </p>
                                                                    </div>

                                                                </div>
                                                            </div>

                                                        </div>
                                                    </div>

                                                </div>

                                                <div class="mt-20 w-full">
                                                    <div class="w-full flex justify-center">
                                                        <button id="signup"
                                                            class="my-3 py-1 w-[220px] text-slate-50 text-xl font-semibold flex justify-center border border-slate-50 rounded-xl cursor-pointer hover:bg-white hover:text-red-500 hover:scale-105"
                                                            @click="toggleAccessTab" @mouseover="hoverOnSignUp(true)"
                                                            @mouseleave="hoverOnSignUp(false)">
                                                            {{ state.buttontext }}
                                                        </button>
                                                    </div>
                                                    <div class="w-full flex justify-center">
                                                        <button id="login" @click="toggleAccessTab"
                                                            class="my-3 py-1 w-[220px] text-slate-50 text-xl font-semibold flex justify-center border border-slate-50 rounded-xl cursor-pointer hover:bg-white hover:text-red-500 hover:scale-105">
                                                            Log In
                                                        </button>
                                                    </div>
                                                </div>
                                            </div>
                                            <div v-show="creatingAccount">
                                                <div class="w-full flex justify-center">
                                                    <div class="pt-10 text-white text-2xl font-bold">
                                                        Create An Account
                                                    </div>
                                                </div>
                                                <div class="w-full flex justify-center">
                                                    <div
                                                        class="my-5 h-[350px] w-[350px] rounded-lg border border-white flex items-center">
                                                        <div>
                                                            <div class="grid grid-cols-2 mx-2.5 pt-5">
                                                                <div class="col-span-1 px-1">
                                                                    <div class="relative">
                                                                        <input type="text" id="first_name"
                                                                            class="block px-2.5 pb-1.5 pt-3 w-full text-sm text-gray-900 cursor-text bg-transparent rounded-lg border-1 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-none focus:bg-slate-100 peer"
                                                                            placeholder=" " />
                                                                        <label for="first_name"
                                                                            class="absolute text-sm cursor-text text-slate-100 dark:text-gray-400 duration-300 transform -translate-y-3 scale-75 top-1 z-10 origin-[0] bg-transparent dark:bg-gray-900 px-2 peer-focus:px-2 peer-focus:pt-1 peer-focus:text-red-500 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:top-1/2 peer-focus:top-1 peer-focus:scale-75 peer-focus:-translate-y-3 left-1">First
                                                                            Name</label>
                                                                    </div>
                                                                </div>
                                                                <div class="col-span-1 px-1">
                                                                    <div class="relative">
                                                                        <input type="text" id="last_name"
                                                                            class="block px-2.5 pb-1.5 pt-3 w-full text-sm cursor-text text-gray-900 bg-transparent rounded-lg border-1 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-none focus:bg-slate-100 peer"
                                                                            placeholder=" " />
                                                                        <label for="last_name"
                                                                            class="absolute text-sm cursor-text text-slate-100 dark:text-gray-400 duration-300 transform -translate-y-3 scale-75 top-1 z-10 origin-[0] bg-transparent dark:bg-gray-900 px-2 peer-focus:px-2 peer-focus:pt-1 peer-focus:text-red-500 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:top-1/2 peer-focus:top-1 peer-focus:scale-75 peer-focus:-translate-y-3 left-1">Last
                                                                            Name</label>
                                                                    </div>
                                                                </div>
                                                            </div>
                                                            <div class="mx-2.5 pt-5 ">
                                                                <div class="px-1">
                                                                    <div class="relative">
                                                                        <input type="text" id="employee_id"
                                                                            class="block px-2.5 pb-1.5 pt-3 w-full text-sm cursor-text text-gray-900 bg-transparent rounded-lg border-1 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-none focus:bg-slate-100 peer"
                                                                            placeholder=" " />
                                                                        <label for="employee_id"
                                                                            class="absolute text-sm cursor-text text-slate-100 dark:text-gray-400 duration-300 transform -translate-y-3 scale-75 top-1 z-10 origin-[0] bg-transparent dark:bg-gray-900 px-2 peer-focus:px-2 peer-focus:pt-1 peer-focus:text-red-500 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:top-1/2 peer-focus:top-1 peer-focus:scale-75 peer-focus:-translate-y-3 left-1">Employee
                                                                            ID Number</label>
                                                                    </div>
                                                                </div>
                                                            </div>
                                                            <div class="mx-2.5 pt-5 ">
                                                                <div class="px-1">
                                                                    <div class="relative">
                                                                        <input type="text" id="email"
                                                                            class="block px-2.5 pb-1.5 pt-3 w-full text-sm cursor-text text-gray-900 bg-transparent rounded-lg border-1 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-none focus:bg-slate-100 peer"
                                                                            placeholder=" " />
                                                                        <label for="email"
                                                                            class="absolute text-sm cursor-text text-slate-100 dark:text-gray-400 duration-300 transform -translate-y-3 scale-75 top-1 z-10 origin-[0] bg-transparent dark:bg-gray-900 px-2 peer-focus:px-2 peer-focus:pt-1 peer-focus:text-red-500 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:top-1/2 peer-focus:top-1 peer-focus:scale-75 peer-focus:-translate-y-3 left-1">Organisation
                                                                            Email</label>
                                                                    </div>
                                                                </div>
                                                            </div>
                                                            <div class="mx-2.5 pt-5 flex">
                                                                <div class="px-1">
                                                                    <div class="relative">
                                                                        <input type="text" id="password"
                                                                            class="block px-2.5 pb-1.5 pt-3 w-full text-sm cursor-text text-gray-900 bg-transparent rounded-lg border-1 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-none focus:bg-slate-100 peer"
                                                                            placeholder=" " />
                                                                        <label for="password"
                                                                            class="absolute text-sm cursor-text text-slate-100 dark:text-gray-400 duration-300 transform -translate-y-3 scale-75 top-1 z-10 origin-[0] bg-transparent dark:bg-gray-900 px-2 peer-focus:px-2 peer-focus:pt-1 peer-focus:text-red-500 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:top-1/2 peer-focus:top-1 peer-focus:scale-75 peer-focus:-translate-y-3 left-1">Password</label>
                                                                    </div>
                                                                </div>
                                                                <div class="px-1">
                                                                    <div class="relative">
                                                                        <input type="text" id="retype_password"
                                                                            class="block px-2.5 pb-1.5 pt-3 w-full text-sm cursor-text text-gray-900 bg-transparent rounded-lg border-1 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-none focus:bg-slate-100 peer"
                                                                            placeholder=" " />
                                                                        <label for="retype_password"
                                                                            class="absolute text-sm cursor-text text-slate-100 dark:text-gray-400 duration-300 transform -translate-y-3 scale-75 top-1 z-10 origin-[0] bg-transparent dark:bg-gray-900 px-2 peer-focus:px-2 peer-focus:pt-1 peer-focus:text-red-500 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:top-1/2 peer-focus:top-1 peer-focus:scale-75 peer-focus:-translate-y-3 left-1">Re-Type
                                                                            Password</label>
                                                                    </div>
                                                                </div>
                                                            </div>

                                                            <div class="mt-5 w-full">
                                                                <div class="w-full flex justify-center">
                                                                    <button id="signup"
                                                                        class="my-3 py-1 w-[150px] text-slate-50 text-base font-semibold flex justify-center border border-slate-50 rounded-xl cursor-pointer hover:bg-white hover:text-red-500 hover:scale-105">
                                                                        {{ state.buttontext }}
                                                                    </button>
                                                                </div>

                                                            </div>
                                                        </div>
                                                    </div>
                                                </div>
                                                <div class=" w-full flex items-center justify-center">
                                                    <p class="pr-1 text-slate-200 text-sm font-semibold">
                                                        Already have an account?
                                                    </p>
                                                    <p id="login" @click="toggleAccessTab"
                                                        class="pt-0.5 text-slate-50 text-xs font-semibold flex justify-center rounded-xl cursor-pointer  hover:scale-110">
                                                        Log In
                                                    </p>
                                                </div>
                                            </div>

                                            <div v-show="loggingIn">
                                                <div class="w-full flex justify-center">
                                                    <div class="pt-10 text-white text-2xl font-bold">
                                                        Log In
                                                    </div>
                                                </div>
                                                <div class="w-full flex justify-center">
                                                    <div
                                                        class="my-5 h-[250px] w-[350px] rounded-lg border border-white flex items-center">
                                                        <div class="w-full">
                                                            <div class="mx-4 pt-5 ">
                                                                <div class="px-1">
                                                                    <div class="relative hover:scale-105">
                                                                        <input type="text" id="login_email"
                                                                            class="block px-2.5 pb-1.5 pt-3 w-full text-sm cursor-text text-gray-900 bg-transparent rounded-lg border-1 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-none focus:bg-slate-100 peer"
                                                                            placeholder=" " />
                                                                        <label for="login_email"
                                                                            class="absolute text-sm cursor-text text-slate-100 dark:text-gray-400 duration-300 transform -translate-y-3 scale-75 top-1 z-10 origin-[0] bg-transparent dark:bg-gray-900 px-2 peer-focus:px-2 peer-focus:pt-1 peer-focus:text-red-500 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:top-1/2 peer-focus:top-1 peer-focus:scale-75 peer-focus:-translate-y-3 left-1">Organisation
                                                                            Email</label>
                                                                    </div>
                                                                </div>
                                                            </div>
                                                            <div class="mx-4 pt-5 ">
                                                                <div class="px-1">
                                                                    <div class="relative hover:scale-105">
                                                                        <input type="text" id="login_password"
                                                                            class="block px-2.5 pb-1.5 pt-3 w-full text-sm cursor-text text-gray-900 bg-transparent rounded-lg border-1 border-gray-300 appearance-none dark:text-white dark:border-gray-600 dark:focus:border-blue-500 focus:outline-none focus:ring-0 focus:border-none focus:bg-slate-100 peer"
                                                                            placeholder=" " />
                                                                        <label for="login_password"
                                                                            class="absolute text-sm cursor-text text-slate-100 dark:text-gray-400 duration-300 transform -translate-y-3 scale-75 top-1 z-10 origin-[0] bg-transparent dark:bg-gray-900 px-2 peer-focus:px-2 peer-focus:pt-1 peer-focus:text-red-500 peer-focus:dark:text-blue-500 peer-placeholder-shown:scale-100 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:top-1/2 peer-focus:top-1 peer-focus:scale-75 peer-focus:-translate-y-3 left-1">Password</label>
                                                                    </div>
                                                                </div>
                                                            </div>


                                                            <div class="mt-5 w-full">
                                                                <div class="w-full flex justify-center">
                                                                    <button id="login"
                                                                        class="my-3 py-1 w-[150px] text-slate-50 text-base font-semibold flex justify-center border border-slate-50 rounded-xl cursor-pointer hover:bg-white hover:text-red-500 hover:scale-105">
                                                                        Log In
                                                                    </button>
                                                                </div>

                                                            </div>
                                                        </div>
                                                    </div>
                                                </div>
                                                <div class="my-3 w-full flex justify-center">
                                                    <p class="pr-2 text-slate-200 text-sm font-semibold">
                                                        Don't have an account yet?
                                                    </p>
                                                    <p id="signup" @click="toggleAccessTab"
                                                        class="text-slate-50 text-sm font-semibold flex justify-center rounded-xl cursor-pointer  hover:scale-110">
                                                        Sign Up
                                                    </p>
                                                </div>
                                            </div>
                                        </div>

                                        <div class="h-[100px]">
                                            <div class=" w-full h-full flex justify-center items-end">

                                                <div class="text-white text-sm">
                                                    Copyright &copy; 2023 Kyle Smith Designs
                                                </div>
                                            </div>
                                        </div>
                                    </div>

                                </div>
                            </div>
                        </div>
                    </div>
                </div>

            </div>

        </div>
    </div>
</template>

<script setup>
import {
    ChatBubbleLeftIcon,
    UserCircleIcon,
} from '@heroicons/vue/24/outline';
import { reactive, nextTick, computed } from "vue";
import { Head, Link, useForm } from "@inertiajs/inertia-vue3";
import { ref, onMounted, watch } from 'vue';


// const buttonText = 'Sign Up';

const hoverOnSignUp = (isHovering) => {
    if (isHovering) {
        state.buttontext = 'Create Account';
    } else {
        state.buttontext = 'Sign Up';
    }
};

const state = reactive({
    buttontext: 'Sign Up',
    hoversignup: false,
    signupclicked: null,
    loginclicked: null,
})

const creatingAccount = ref(false);
const loggingIn = ref(false);
const isFocused = ref(false);

const toggleCreateAccount = () => {
    creatingAccount.value = true;
    loggingIn.value = false;
}

const fieldFilled = () => {
    isFocused.value = !isFocused.value;
}



function toggleAccessTab(event) {
    if (event) {
        switch (event.target.id) {
            case "signup":
                creatingAccount.value = true;
                loggingIn.value = false;
                break;
            // logInClicked.value = false;
            case "login":
                // signupclicked.value = false;
                creatingAccount.value = false;
                loggingIn.value = true;
                break;
            case "options":
                creatingAccount.value = false;
                loggingIn.value = false;
                break;
            default:
                break;
        }
    }
}

</script>

<style>
.background1 {
    background-color: #e8e6ec;
    background-color: #e4e4e4;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='28' height='49' viewBox='0 0 28 49'%3E%3Cg fill-rule='evenodd'%3E%3Cg id='hexagons' fill='%23ffffff' fill-opacity='0.4' fill-rule='nonzero'%3E%3Cpath d='M13.99 9.25l13 7.5v15l-13 7.5L1 31.75v-15l12.99-7.5zM3 17.9v12.7l10.99 6.34 11-6.35V17.9l-11-6.34L3 17.9zM0 15l12.98-7.5V0h-2v6.35L0 12.69v2.3zm0 18.5L12.98 41v8h-2v-6.85L0 35.81v-2.3zM15 0v7.5L27.99 15H28v-2.31h-.01L17 6.35V0h-2zm0 49v-8l12.99-7.5H28v2.31h-.01L17 42.15V49h-2z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
}

@keyframes bounce-pause-bounce {

    0%,
    100% {
        transform: translateY(0);
    }

    80% {
        transform: translateY(-30px);
        /* Adjust the bounce height as needed */
    }

    75%,
    50% {
        transform: translateY(0);
    }
}

/* Apply the custom animation to the element */
.custom-bounce-pause-bounce {
    animation: bounce-pause-bounce 3s infinite;
    /* Adjust the duration (2s in this example) */
}
</style>