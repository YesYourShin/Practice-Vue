<script>
import memoApi from '../apis/memos';

export default {
    name: 'Home',
    data(){
        return {
            memos:[],
        }
    },
    method(){
        memoApi.getMemos()
        .then(res=>{
            this.memos = res.data
        })
        .catch(()=>{
            
        })
    }
}
</script>