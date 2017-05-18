<template>
    <div class="container">
        <div class="row">
            <div class="col-sm-12">
                <create-task @created="pushTask"></create-task>
            </div>
        </div>
        <div class="row">
            <div class="col-sm-12" v-for="task in tasks">
                <div class="panel panel-default">
                    <div class="panel-body">
                        <div class="pull-left">{{ task.title }}</div>
                        <div class="pull-right">
                            <button class="btn btn-danger btn-sm" @click.prevent="deleteTask(task)">
                                Delete
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        data() {
            return {
                tasks: []
            }
        },

        methods: {
            pushTask(task) {
                this.tasks.unshift(task);
            },

            deleteTask(task) {
                this.tasks.splice(this.tasks.indexOf(task), 1);
            }
        }
    }
</script>
