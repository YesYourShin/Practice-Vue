<!-- <template>
    <div id="app">
        <h1>Welcome {{userId}}</h1>
        <input v-model="newId" type="text"><button @click="saveUserId">Save</button><br>
        <button @click="updateReviews">Update</button>
        <h1>{{reviewCount}}</h1>
        <ul>
            <li v-for="r in reviews" :key="r.id">
                <p> {{r.body}}</p>
            </li>
        </ul>
    </div>
</template> -->

<template>
    <div id="app">
        <h1>Welcome {{userId}}</h1>
        <v-text-field label="new user id" v-model="newId"></v-text-field>
        <v-btn @click="saveUserId" elevation="2">Save</v-btn><br>
        <v-btn @click="updateReviews" color="primary">Update</v-btn>
        <h1>{{reviewCount}}</h1>
        <v-simple-table>
            <template v-slot:default>
                <thead>
                    <tr>
                        <th>Email</th>
                        <th>Comment</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="item in reviews" :key="item.id">
                        <td>{{item.email}}</td>
                        <td>{{item.body}}</td>
                    </tr>
                </tbody>
            </template>
        </v-simple-table>
    </div>
</template>

<script>
import {mapState, mapGetters, mapMutations, mapActions} from 'vuex'
export default{
    data() {
        return { newId:''}
    },
    computed:{
        ...mapState({
            userId:state=>state.user.userId
        }),
        ...mapState('reviews', {
            reviews:state=>state.reviews
        }),
        ...mapGetters('reviews', ['reviewCount'])
    },
    methods:{
        ...mapMutations(['updateUserId']),
        ...mapActions('reviews', ['getReviews']),
        saveUserId(){
            this.updateUserId(this.newId)
        },
        updateReviews(){
            this.getReviews()
        }
    }
};
</script>