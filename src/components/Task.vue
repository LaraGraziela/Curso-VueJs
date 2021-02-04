<template>
    <div>
        <!-- MOSTRAR UMA LISTA DE TAREFAS ATRAVÉS DO BOTÃO -->
        <h1>Tarefas:</h1>
        
        <button @click="mostrarLista">Ver Lista</button>
        <br>

        <ul v-if="showList">
            <li v-for="(task, index) in tasks"
                @dblclick="completa(task)"
                :key="`${task}-${index}`">
                {{task.name}}
                <button @click="remove(task)">&times;</button>
            </li>
        </ul>
    </div>
</template>

<script>
 
export default {
    //LISTA DE TAREFAS
    data: () => ({
        showList: false,
        tasks: [
            {name: 'Fazer o curso de Vue', isDone: false},
            {name: 'Ficar boa no Vue', isDone: false},
            {name: 'Ficar rica', isDone: false}
        ]
    }),
    //APAGAR O ITEM DE UMA LISTA
    methods: {
        mostrarLista(){
            this.showList = !this.showList
        },
        complete(task){
            this.tasks = this.tasks.map(t => {
                if (t.name === task.name) {
                    return {...t, isDone: !t.isDone}
                }
                return {...t}
            })
        },
        remove(task){
            this.tasks = this.tasks.filter(t => t.name !== task.name)
        }
    }
}
</script>

<style>
    
</style>