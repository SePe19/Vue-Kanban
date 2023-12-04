<script>
import draggable from 'vuedraggable'

export default {
    components: {
        draggable
    },
    data() {
        return {
            todoList: [
                {
                    title: 'Push-ups',
                    description: 'Do 10 pushups with your hands placed in a wide position',
                    id: 1,
                    status: 0
                },
                {
                    title: 'Squats',
                    description: 'Perform 15 squats with proper form and controlled movement',
                    id: 2,
                    status: 0
                },
                {
                    title: 'Plank',
                    description: 'Hold a plank position for 1 minute, engaging your core muscles',
                    id: 3,
                    status: 0
                },
                {
                    title: 'Jumping Jacks',
                    description: 'Complete 20 jumping jacks with full range of motion',
                    id: 4,
                    status: 0
                }
            ],
            doingList: [
                {
                    title: 'Running',
                    description: 'Jog for 20 minutes at a moderate pace',
                    id: 5,
                    status: 1
                }
            ],
            doneList: [
                {
                    title: 'Burpees',
                    description: 'Finish a set of 12 burpees with proper form',
                    id: 6,
                    status: 2
                }
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
                        <div class="kanban-list-item-title">
                            {{ element.title }}: 
                        </div>
                        <div class="kanban-list-item-description">
                            {{ element.description }}
                        </div>
                    </div>
                </template>
            </draggable>
        </div>

        <div class="kanban-column">
            <h3 class="kanban-title">DOING</h3>
            <draggable class="kanban-list" :list="doingList" group="exercises" @change="log">
                <template v-slot:item="{ element }">
                    <div class="kanban-list-item">
                        <div class="kanban-list-item-title">
                            {{ element.title }}: 
                        </div>
                        <div class="kanban-list-item-description">
                            {{ element.description }}
                        </div>
                    </div>
                </template>
            </draggable>
        </div>

        <div class="kanban-column">
            <h3 class="kanban-title">DONE</h3>
            <draggable class="kanban-list" :list="doneList" group="exercises" @change="log">
                <template v-slot:item="{ element }">
                    <div class="kanban-list-item">
                        <div class="kanban-list-item-title">
                            {{ element.title }}: 
                        </div>
                        <div class="kanban-list-item-description">
                            {{ element.description }}
                        </div>
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
    padding: 5px 5px;
    min-height: calc(50% - 20px);
    display: table;
}

.kanban-list {
    margin-bottom: 5px;
}

.kanban-title {
    color: black !important;
    font-weight: 700 !important;
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

.kanban-list-item-title {
    font-weight: 500;
    border-bottom: 1px solid #e0e0e0;
    padding: 5px;
}

.kanban-list-item-description {
    padding: 5px;
}
</style>