<template>
    <div id="app">
        <h1>Menus</h1>
        <h1>{{ menu_name }}</h1>
        <h1>{{ searched_menu }}</h1>
        <ul>
            <li v-for="menu in menus" :key="menu.id">
                <a>{{ menu.name }}</a>
            </li>
        </ul>
    </div>
</template>

<script>
import MenuList from './MenuList.vue'
export default{
    components: {
        MenuList
    },
    name:'Menus',
    computed:{
        data() {
            return {
                menus:[{
                    id:1, name="a", price:10000
                }, {
                    id:2, name="b", price:10000
                }, {
                    id:3, name="c", price:10000
                }]
            }

        },
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
            const id = this.$route.query.menu_id
            if(id=='1')
                return '아이스 아메리카노'
            else if(id=='2')
                return '카페라떼'
            else
                return ''
        }
    }
};
</script>