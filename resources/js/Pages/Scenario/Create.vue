<template>
    <app-layout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Fallbeispiele
            </h2>
        </template>

        <div>
            <div class="max-w-7xl mx-auto py-10 sm:px-6 lg:px-8">
                <div class="bg-white h-screen overflow-hidden shadow-xl sm:rounded-lg">


                    <form @submit.prevent="submitted">

                        <div class="col-span-6 sm:col-span-4">
                            <jet-label for="current_password" value="Current Password" />
                            <jet-input id="current_password" type="password" class="mt-1 block w-full" dv-model="" ref="current_password" autocomplete="current-password" />
                            <jet-input-error d:message="" class="mt-2" />
                        </div>


                         <vue-nestable v-model="measures">
                            <vue-nestable-handle
                            slot-scope="{ item }"
                            :item="item">
                            <i class="far fa-pointer"></i>{{ item.name }}
                            </vue-nestable-handle>
                        </vue-nestable>

                    </form>
                </div>
            </div>
        </div>
    </app-layout>
</template>

<script>
    import AppLayout from '@/Layouts/AppLayout'
    import { VueNestable, VueNestableHandle } from 'vue-nestable'
    import JetLabel from '@/Jetstream/Label'
    import JetInput from '@/Jetstream/Input'
    import JetInputError from '@/Jetstream/InputError'

    export default {
        components: {
            AppLayout,
            VueNestable,
            VueNestableHandle,
            JetLabel,
            JetInput,
            JetInputError
        },

        data() {
            return {
                measures: [
                    {
                        id: 1,
                        name: "Primary Survey",
                        children: [],
                    },
                    {
                        id: 2,
                        name: "A",
                        children: [],
                    },
                    {
                        id: 3,
                        name: "Kopf überstrecken",
                        children: [],
                    },
                    {
                        id: 4,
                        name: "Mundraumkontrolle",
                        children: [],
                    },
                ]
            }
        }
    }
</script>
