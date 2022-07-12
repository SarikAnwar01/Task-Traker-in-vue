<template>
    <div  :key="task.id" v-for="task in tasks">
  <Task @toggle-reminder="$emit('toggle-reminder',task.id)" @delete="$emit('delete',task.id)" :task="task"/>

    </div>
</template>

<script>
import Task from './Task'

export default {
    name: "Tasks ",
    props:{
        tasks: Array
    },
    components: {
        Task
    },
    emits:['delete','toggle-reminder'],
}
</script>