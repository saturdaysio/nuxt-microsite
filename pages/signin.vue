<template>
    <div class="flex flex-col h-screen justify-between">

        <NavBar />

        <section id="default" class="container max-w-md mx-auto px-4">

            <div class="">
                <form
                    @submit.prevent="() => (isSignUp ? signUp() : signIn ())"
                    class="rounded px-6 py-8 bg-black-500">

                    <h1 class="text-3xl lg:text-4xl text-center font-bold text-grad-01 pb-8">
                        Sign in
                    </h1>

                    <div id="username" class="mb-8">
                        <label class="block text-white text-sm font-bold mb-2" for="username">
                            Username
                        </label>
                        <input id="username" type="text" placeholder="Username" v-model="email"
                            class=" appearance-none border rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none">
                    </div>

                    <div id="password" class="mb-8">
                        <label class="block text-white text-sm font-bold mb-2" for="password">
                            Password
                        </label>
                        <input id="password" type="current-password" placeholder="********" v-model="password" 
                            class=" appearance-none border rounded w-full py-2 px-4 text-gray-700 mb-2 leading-tight focus:outline-none">
                    </div>

                    <div class="flex flex-col items-center justify-between">
                        <button class="button primary w-full rounded font-bold mb-4" type="button">
                            Sign In
                        </button>

                        <a class="inline-block align-baseline text-sm text-blue hover:text-purple-800" href="/">
                            Forgot Password?
                        </a>
                    </div>

                </form>
            </div>

        </section>

        <Footer />

    </div>
</template>


<script lang="ts" setup>

    const client = useSupabaseClient()
    const email = ref('')
    const password = ref('')
    const isSignUp = ref(false)


    useHead({
        title: 'Saturdays.io - Sign in',
        meta: [
            { name: 'description', content: 'Saturdays.io sign in page' },
            { name: 'keywords', content: 'Saturdays.io, Digital, Studio, Creative, Digital Studio, Creative Studio,' },
        ]
    })


    const signUp = async () => {

        console.log('user', user)
    }

    const signIn = async () => {

        console.log('user', user)
    }

    const user = useSupabaseUser()

    onMounted(() => {
        watchEffect(() => {
        })
    })
</script>


<style lang="scss">

</style>