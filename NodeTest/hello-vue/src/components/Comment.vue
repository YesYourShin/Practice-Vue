<template>
    <div>
    <input type="text" v-model="user">
    <input type="text" v-model="comment">
    <button @click="save">Save</button><br>
    <ul>
        <li v-for="(msg, i) in messages" :key='i'>
            <p>{{ msg.user }}: {{ msg.comment }}</p>
        </li>        
    </ul>
    </div>
</template>

<script>
 export default{
data(){
        return { 
            user:null,
            comment:null,
            messages:[]
        }
    },
    methods:{
        save: function(){
            const message={
                user:this.user,
                comment:this.comment
            };

            this.messages.unshift(message);
            this.user=null
            this.comment=null
        }
    }
}
</script>