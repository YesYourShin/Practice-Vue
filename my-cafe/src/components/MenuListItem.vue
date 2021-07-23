<template>
    <ul><button @click="$emit('link', )">{{ searched_menu }}</button></ul>
</template>

<script>
export default{
    name:'Menus',
    computed:{
        menu_name(){
            const id = this.$route.params.menu_id
            if(id=='1')
                return '아이스 아메리카노'
            else if(id=='2')
                return '카페라떼'
            else
                return ''
        },
        searched_menu(){
            if(this.query_id)
                return '아이스 아메리카노'
            else
                return 'd'
        }
    }
};
</script>