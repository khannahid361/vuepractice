<template>
    <div>
        <h1>Update Post</h1>
        <form @submit.prevent="updatePost">
            <div>
                <label for="userId">User Id</label>
                <input type="text" id="userId" v-model="formData.userId" required>
            </div>
            <div>
                <label for="title">Title</label>
                <input type="text" id="title" v-model="formData.title" required>
            </div>
            <div>
                <label for="body">Body</label>
                <input type="text" id="body" v-model="formData.body" required>
            </div>
            <div>
                <button type="submit">Update</button>
            </div>
        </form>
    </div>
</template>

<script>
import axios from 'axios';
    export default {
        name: 'UpdatePost',
        data() {
            return {
                formData: {
                    userId: '',
                    title: '',
                    body: ''
                }
            }
        },
        methods: {
            updatePost() {
                axios
                .put('https://jsonplaceholder.typicode.com/posts/1', this.formData)
                .then((response)=> {
                    console.log(response.data);
                })
                .catch((error)=> {
                    console.log(error);
                })
            }
        },
    }
</script>

<style scoped>

</style>