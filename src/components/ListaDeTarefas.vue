<script setup>
const props = defineProps(['tarefas']);
</script>

<template>
    <ul v-if="tarefas.length > 0" class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada"
                :id="tarefa.titulo" type="checkbox">
            <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
    <h3 v-else class="mt-4 ms-4">
        Não existem tarefas
    </h3>
</template>

<style scoped>
.done {
    text-decoration: line-through;
}
</style>