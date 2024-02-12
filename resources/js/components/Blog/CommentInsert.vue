<template>
    <div class="card p-2 mb-3" v-if="blog_details && blog_details.id">
        <div class="mb-3">
            <input type="text" class="form-control" v-model="comment_body.name" placeholder="type name here">
        </div>
        <div class="mb-3">
            <textarea class="form-control" v-model="comment_body.comment" placeholder="comment here"></textarea>
        </div>
            <button type="button" class="btn btn-primary btn-sm" @click="comment_submit()">comment</button>
    </div>
</template>

<script>
export default {
    props:[
        'blog_details',
        'post_comment'
    ],
     data() {
        return{
            comment_body:{

                    blog_id:this.blog_details.id,
                    name:"",
                    comment:""
            }

        }
    },
    methods:{
        comment_submit(){
            this.comment_body.blog_id =this.blog_details.id;
            // console.log(this.comment_body);
            // console.log(this.blog_details.id);
            this.post_comment(this.comment_body);
            this.comment_body={
                    blog_id:'',
                    name:"",
                    comment:""
            }

        }
    }
}
</script>

<style>

</style>
