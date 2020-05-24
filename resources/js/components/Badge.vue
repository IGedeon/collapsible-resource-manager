<template>

    <div class="flex items-center">

        <div class="dim">
            <slot/>
        </div>

        <div v-if="label" class="badge rounded-full text-xxs ml-2 self-start">
            {{ label | capitalize }}
        </div>

    </div>

</template>

<script>

    export default {
        name: 'Badge',
        props: {
            label: {
                type: String
            }
        },
        filters: {
          capitalize: function (value) {
            return (value + '').toLowerCase().replace(/(?<= )[^\s]|^./g, a=>a.toUpperCase());
          }
        }
    }

</script>

<style scoped>

    .badge {
        background: var(--collapsible-menu-badge-color, var(--primary));
        padding: 0.15rem 0.35rem;
        align-self: center;
    }

    .text-xxs {
        font-size: .60rem
    }

</style>
