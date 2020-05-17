<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Task Form</div>

                    <div class="card-body">
                        <form action="./api/task" method="POST" @submit.prevent="addTask()">
                            <div class="form-group">
                                <input type="text" name="title" v-model="title" placeholder="Task Title" class="form-control">
    
                            </div>
                            <div class="form-group">
                                <input type="submit" value="Add Task"  class="btn btn-info">
                                
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {

        data(){
            return{
                title: ''
            }
        },
        mounted() {
            console.log('Component mounted.')
        },
        methods:{
            addTask(){
                axios.post('./api/task',{title:this.title});
                alert('Adding Task');
            }
            
        }
    }
</script>


<style></style>
