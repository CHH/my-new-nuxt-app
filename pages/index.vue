<script setup>

const query = gql`
    query {
        characters {
            results {
                name
            }
        }
    }
`

const { data, error } = useAsyncQuery(query)
</script>

<template>
    <div class="grid grid-cols-3 p-3 gap-3">
        <div
            class="p-3 bg-gray-500 shadow rounded"
            v-for="(character) in data?.characters?.results"
        >
            {{ character.name }}
        </div>
    </div>
</template>