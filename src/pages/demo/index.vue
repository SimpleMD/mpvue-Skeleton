<template>
  <div>
     <skeleton selector="skeleton"
          loading="spin"
          bgcolor="#FFF"
          v-if="showSkeleton"></skeleton>

            <!--index.wxml-->
            <div class="container skeleton">
            <div class="userinfo">
            <block>
                <image class="userinfo-avatar skeleton-radius" :src="userInfo.avatarUrl"
                        mode="cover"></image>
                <text class="userinfo-nickname skeleton-rect">{{userInfo.nickName}}</text>
            </block>
            </div>
            <div style="margin: 20px 0">
            <div v-for="(item,index) in lists" :index='index' :key='item'  class="lists">
                <icon type="success" size="20" class="list skeleton-radius"/>
                <text class="skeleton-rect">{{item}}</text>
            </div>
            </div>

            <div class="usermotto">
            <text class="user-motto skeleton-rect">{{motto}}</text>
            </div>
           
              <div class=" skeleton-rect">{{userInfo.nickName}}asdasdasdasdasdddddddddd</div>

   
            </div>


  </div>
</template>

<script>
import skeleton from '@/components/skeleton'

export default {
  data () {
    return {
        motto: 'Hello World',
        userInfo: {
        avatarUrl: 'https://wx.qlogo.cn/mmopen/vi_32/SYiaiba5faeraYBoQCWdsBX4hSjFKiawzhIpnXjejDtjmiaFqMqhIlRBqR7IVdbKE51npeF6X1cXxtDQD2bzehgqMA/132',
        nickName: 'jayzou'
        },
        lists: [
        'aslkdnoakjbsnfkajbfk',
        'qwrwfhbfdvndgndghndeghsdfh',
        'qweqwtefhfhgmjfgjdfghaefdhsdfgdfh',
        ],
        showSkeleton: true
    }
  },

  components: {
   skeleton
  },

  methods: {

  },

  created () {
		const that = this;
		setTimeout(() => {
        that.showSkeleton = false
		}, 3000)
  }
}
</script>

<style scoped>
/**index.wxss**/
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}

.userinfo-nickname {
  color: #aaa;
}

.usermotto {
  margin-top: 200px;
}

.lists{
  margin: 10px 0;
}
.list{
  margin-right: 10px;
}
</style>
