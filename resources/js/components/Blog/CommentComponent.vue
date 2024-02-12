<template>

    <div>
        <comment-insert :blog_details="blog_details" :post_comment="post_comment"></comment-insert>
        <div class="card p-2 " v-for="comment in selected_comments" :key="comment.id">
            <div class="identity d-flex align-items-end">
                <img style="width: 40px ; height:40px" src="https://static.vecteezy.com/system/resources/previews/019/896/008/original/male-user-avatar-icon-in-flat-design-style-person-signs-illustration-png.png" alt="">
                <h5 class="mb-0 ms-2">{{comment.name}}</h5>
            </div>
            <p>{{comment.comment}}</p>
        </div>
    </div>

</template>

<script>
import CommentInsert from './CommentInsert.vue'
export default {
  components: { CommentInsert },
    props:[
        'selected_comments',
        'blog_details',
        'post_comment'
    ]
}
</script>

<style>

</style>
