<template>
    <div>
        <div class="container">
            <div class="row">
                <div class="col-lg-6">
                    <div class="card mb-2" v-for="blog in blog_lists" :key="blog.id">
                        <div @click="get_blog_details(blog)" class="card-body">
                            <h3 class="m-0">{{blog.title}}</h3>
                            <p class="m-0">{{blog.description}}</p>
                        </div>
                    </div>
                </div>
                <div class="col-lg-6">
                    <BlogDetailComponent :blog_details="blog_details"
                                        :selected_comments="selected_comments"
                                        :post_comment="post_comment"></BlogDetailComponent>
                </div>
            </div>
        </div>
    </div>

</template>

<script>
import BlogDetailComponent from './BlogDetailComponent.vue';



export default {
    components: {
        BlogDetailComponent
    },
    data() {
        return{
            blog_lists:[
                {
                    id:1,
                    title: "blog 1",
                    description: "something to see",
                },
                {
                    id:2,
                    title: "blog 2",
                    description: "something something to see sfdsf dsf dsg rg r gt ht h t ht something to see sfdsf dsf dsg rg r gt ht h t ht something to see sfdsf dsf dsg rg r gt ht h t ht to seewerew",
                },
                {
                    id:3,
                    title: "blog 3",
                    description: "something something to see sfdsf dsf dsg rg r gt ht h t ht something to see sfdsf dsf dsg rg r gt ht h t ht something to see sfdsf dsf dsg rg r gt ht h t ht to see sdewwe2222",
                },
                {
                    id:4,
                    title: "blog 4",
                    description: "something to see 324324 something to see sfdsf dsf dsg rg r gt ht h t ht something to see sfdsf dsf dsg rg r gt ht h t ht something to see sfdsf dsf dsg rg r gt ht h t ht",
                },
                {
                    id:5,
                    title: "blog 5",
                    description: "anything to see fewxc something to see sfdsf dsf dsg rg r gt ht h t ht something to see sfdsf dsf dsg rg r gt ht h t ht something to see sfdsf dsf dsg rg r gt ht h t ht",
                }
            ],
            blog_details:[
                {
                    id:'',
                    title: "",
                    description: "",
                }
            ],
            comments:[
                {
                    id:1,
                    blog_id:1,
                    name:'wtasnimul hasan',
                    comment:'1ything to see fewxc ing to se'
                },
                {
                    id:2,
                    blog_id:1,
                    name:'stasnimul hasan',
                    comment:'2ything to see fewxc ing to se'
                },
                {
                    id:3,
                    blog_id:2,
                    name:'ktasnimul hasan',
                    comment:'3ything to see fewxc ing to se'
                },
                {
                    id:4,
                    blog_id:3,
                    name:'jtasnimul hasan',
                    comment:'4ything to see fewxc ing to se'
                },
                {
                    id:5,
                    blog_id:4,
                    name:'ntasnimul hasan',
                    comment:'5ything to see fewxc ing to se'
                },
                {
                    id:6,
                    blog_id:3,
                    name:'xtasnimul hasan',
                    comment:'6ything to see fewxc ing to se'
                },
                {
                    id:7,
                    blog_id:4,
                    name:'ntasnimul hasan',
                    comment:'7ything to see fewxc ing to se'
                },
                {
                    id:8,
                    blog_id:5,
                    name:'ytasnimul hasan',
                    comment:'8ything to see fewxc ing to se'
                },
                {
                    id:9,
                    blog_id:5,
                    name:'rtasnimul hasan',
                    comment:'9ything to see fewxc ing to se'
                },
                {
                    id:10,
                    blog_id:5,
                    name:'etasnimul hasan',
                    comment:'10ything to see fewxc ing to se'
                },
            ],
            selected_comments:[

            ]

        }
    },
    methods:{
        get_blog_details(blog){
            // console.log(blog.title);
            // this.blog_details.id =blog.id;
            // this.blog_details.title =blog.title;
            // this.blog_details.description =blog.description;
            this.blog_details =blog;
            // console.log(this.blog_details.description +'---------');
            this.selected_comments = this.comments.filter((item) => item.blog_id === blog.id)

        },
        post_comment(comment){
            comment.id = this.comments.length + 1;
            // console.log(comment);
            this.selected_comments.unshift(comment);
            this.comments.push(comment);
            // console.log(this.selected_comments);
            // console.log(this.comments);
        }

    }


}
</script>

<style>

</style>
