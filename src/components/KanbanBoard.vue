<script>
import draggable from 'vuedraggable'

export default {
    components: {
        draggable
    },
    data() {
        return {
            todoList: [
                { name: 'Push-ups', id: 1, status: 0},
                { name: 'Squats', id: 2, status: 0},
                { name: 'Plank', id: 3, status: 0},
                { name: 'Jumping Jacks', id: 4, status: 0},
            ],
            doingList: [
                { name: 'Running', id: 5, status: 1},
            ],
            doneList: [
                { name: 'Burpees', id: 6, status: 2},
            ]
        }
    },
    methods: {
        log: function (evt) {
            window.console.log(evt)
        }
    }
}
</script>

<template>
    <div class="kanban-board">
        <div class="kanban-column">
            <h3 class="kanban-title">TODO</h3>
            <draggable class="kanban-list" :list="todoList" group="exercises" @change="log">
                <template v-slot:item="{ element }">
                    <div class="kanban-list-item">
                        {{ element.name }}
                    </div>
                </template>
            </draggable>
        </div>

        <div class="kanban-column">
            <h3 class="kanban-title">DOING</h3>
            <draggable class="kanban-list" :list="doingList" group="exercises" @change="log">
                <template v-slot:item="{ element }">
                    <div class="kanban-list-item">
                        {{ element.name }}
                    </div>
                </template>
            </draggable>
        </div>

        <div class="kanban-column">
            <h3 class="kanban-title">DONE</h3>
            <draggable class="kanban-list" :list="doneList" group="exercises" @change="log">
                <template v-slot:item="{ element }">
                    <div class="kanban-list-item">
                        {{ element.name }}
                    </div>
                </template>
            </draggable>
        </div>
    </div>
</template>

<style scoped>
.kanban-board {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* Three columns with equal width */
    gap: 20px;
    display: normal;
    padding-bottom: 0px;
}

.kanban-column {
    float: left;
    clear: right;
    border-radius: 5px;
    background-color: #eaebed;
    min-height: 600px;
    width: 300px;
    padding-bottom: 0px;
    padding-left: 6px;
    min-height: calc(50% - 20px);
    display: table;
}

.kanban-list {
}

.kanban-title {
    color: black !important;
    font-weight: bold !important;
}

.kanban-list-item {
    color: black !important;
    cursor: pointer;
}

.col-3 {
    color: white !important;
    background-color: black !important;
}
</style>


<style scoped>
.kanban-board {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* Three columns with equal width */
    gap: 20px;
    display: normal;
    padding-bottom: 0px;
}

.kanban-column {
    float: left;
    clear: right;
    border-radius: 5px;
    background-color: #eaebed;
    min-height: 600px;
    width: 300px;
    padding: 5px 5px;
    min-height: calc(50% - 20px);
    display: table;
}

.kanban-list {
    margin-bottom: 5px;
}

.kanban-title {
    color: black !important;
    font-weight: bold !important;
}

.kanban-list-item {
    border: 1px solid #e0e0e0;
    border-radius: 5px;
    padding: 5px;
    background-color: #ffffff;
    margin-top: 5px;
    color: black !important;
    cursor: pointer;
}

.col-3 {
    color: white !important;
    background-color: black !important;
}
</style>

<style scoped>
.kanban-board {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* Three columns with equal width */
    gap: 20px;
    display: normal;
    padding-bottom: 0px;
}

.kanban-column {
    float: left;
    clear: right;
    border-radius: 5px;
    background-color: #eaebed;
    min-height: 600px;
    width: 300px;
    padding-bottom: 0px;
    padding-left: 6px;
    min-height: calc(50% - 20px);
    display: table;
}

.kanban-list {
}

.kanban-title {
    color: black !important;
    font-weight: bold !important;
}

.kanban-list-item {
    color: black !important;
    cursor: pointer;
}

.col-3 {
    color: white !important;
    background-color: black !important;
}
</style>
