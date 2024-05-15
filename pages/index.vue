<template>
    <MainLayout>
        <div id="IndexPage" class="w-full overflow-auto">
            <div class="mx-auto max-w-[500px] overflow-hidden">
                <div id="Posts" class="px-4 max-w-[600px] mx-auto">

                    <div v-if="isPosts" v-for="post in posts" :key="post">
                        <Post :post="post" @isDeleted="post = []" />
                    </div>
                </div>
            </div>
        </div>
    </MainLayout>
</template>

<script setup>
import MainLayout from '~/layouts/MainLayout.vue';
import { useUserStore } from '~/stores/user.js';
const userStore = useUserStore()
//const user = useSupabaseUser()

let posts = ref([])
let isPosts = ref(true)
let isLoading = ref(false)

onBeforeMount(() => {
    posts.value = [
        {
            name: 'Tom Ate Banane',
            image: 'https://picsum.photos/id/289/50',
            text: 'Das hier ist mein Threads Post Titel, na klar...',
            picture: 'https://picsum.photos/id/99/1000',
        },
        {
            name: 'Riesen Kobold',
            image: 'https://picsum.photos/id/189/50',
            text: 'Ihr glaub nicht was mir heute passiert ist...',
            picture: 'https://picsum.photos/id/203/1000',
        },
        {
            name: 'Feuerwehrmann3',
            image: 'https://picsum.photos/id/79/50',
            text: 'Hach jaaaa... hach jaa wie herrlich.... hachjaaaaaaaaaaaaaaaaaaaaaaaaa',
            picture: 'https://picsum.photos/id/199/1000',
        },
        {
            name: 'Septimencrusher',
            image: 'https://picsum.photos/id/89/50',
            text: 'Von welchem Tier stammen wohl diese Fußabdrücke? (Hmm, denkender Smiley)',
            picture: 'https://picsum.photos/id/299/1000',
        },
        {
            name: 'Freter Pahm Coaching',
            image: 'https://picsum.photos/id/12/50',
            text: 'Die gute Natur erhöht euer Testosteron. Tschüss und Grüße.',
            picture: 'https://picsum.photos/id/10/1000',
        }
    ]
})
</script>
