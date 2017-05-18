<template>
    <div class="panel panel-default">
        <div class="panel-heading">Create Task</div>
        <div class="panel-body">
            <div class="row">
                <div class="col-sm-12">
                    <div class="form-group">
                        <input type="text" class="form-control" v-model='title' @keyup.enter="createTask">
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
                title: ''
            }
        },

        methods: {
            createTask() {
                let task = {
                    title: this.title
                };

                this.$emit('created', task);
                this.title = '';
            }
        }
    }
</script>
