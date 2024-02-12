<template>
    <div>
        <div class="blog_detail mb-3">
            <div class="card mb-2" >
                <div class="card-body">
                    <h4 class="m-0">{{blog_details.title}}</h4>
                    <p class="m-0">{{blog_details.description}}</p>
                </div>
            </div>
            <!-- <h1>blog details</h1> -->
        </div>
        <hr>
        <div class="comments ">
            <!-- <CommentComponent :selected_comments="selected_comments"></CommentComponent> -->
            <comment-component :selected_comments="selected_comments" :blog_details="blog_details" :post_comment="post_comment"></comment-component>
        </div>
    </div>

</template>

<script>
import CommentComponent from "./CommentComponent.vue";
export default {
    components: {
        CommentComponent
    },
    props:[
        'blog_details',
        'selected_comments',
        'post_comment'
    ]
}
</script>

<style>

</style>
