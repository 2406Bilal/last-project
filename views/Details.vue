<template>
    <div v-if="error"> {{ error}}</div>
    <div v-if="post" class="post">
        <h3>{{ title.title }}</h3>
    </div>
</template>
<script>
import getPosts from '@/components/getPost';
export default{
    props:['id'],
    setup(props){
        const {post , error, load} = getPosts(props.id)

        load();

        return { post, error}
    }
}
</script>