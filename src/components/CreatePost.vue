<template>
    <div>
        <h1>Form Request</h1>
        <form @submit.prevent="createPost">
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
                <button type="submit">Submit</button>
            </div>
        </form>
    </div>
</template>

<script>
    import axios from "axios";
    export default {
        name: 'CreatePost',
        data() {
            return {
                formData : {
                    userId: '',
                    title: '',
                    body: ''
                }
            }
        },
        methods: {
            createPost() {
                axios.post('https://jsonplaceholder.typicode.com/posts', this.formData)
                   .then(response => {
                        console.log(response);
                    })
                   .catch(error => {
                        console.error(error);
                    });
            }
        },
    }
</script>

<style>

</style>