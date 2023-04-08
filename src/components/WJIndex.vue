<template>
  <div>


    <div class="wj_login" v-show="wj_login">
      <div class="wj_login_table">
        <div class="wj_login_username">
          <input v-model="username" name="username" type="text" placeholder="用户名"><br>
        </div>
        <div class="wj_login_password">
          <input v-model="password" name="password" type="password" placeholder="密码"><br>
        </div>
        <div class="wj_login_button">
          <button @click="wj_register_func" type="button">注册</button>
        </div>
      </div>

    </div>

    <div class="wj_index_1001" v-show="wj_index_1001">
      <div class="wj_nav_home">
        <div class="wj_nav_banner" v-show="wj_index_box01">
          <ul class="wj_nav_list">
            <li>
              <!--            <a href="#">-->
              用户：{{ user }}
              <!--            </a>-->
            </li>
            <li>|</li>
            <li>
              <a href="#">
                注册
              </a>
            </li>
            <li>|</li>
            <li>
              <a href="#">
                登录
              </a>
            </li>
            <li>|</li>
            <li>
              <a href="#wj_catdgory_id">
                分类榜单
              </a>
            </li>
            <li>|</li>
            <li>
              <a href="#wj_myshelf_id">
                我的书架
              </a>
            </li>
          </ul>
        </div>
        <div class="wj_nav_logo" v-show="wj_index_box01">
          <img src="../assets/img_index/logo_search.png" alt="图片找不到...">
          <span>万卷读书</span>
        </div>
        <div class="wj_nav_search">
          <img src="../assets/img_index/search_index.png" alt="图片找不到...">
          <input @focus="resumeSearch" @blur="resumeIndex" @change="getBookByKeyword" name="keyword" v-model="keyword" type="text" placeholder="搜索">
        </div>
      </div>

      <div class="wj_search_list" v-show="wj_search_list">
        <ul>
          <a href="#">
            <li v-for="s in this.filterBooks" :key="s.id">
              <img :src="getImgSearch(s)" alt="图片找不到...">
              <div>
                <h4 class="wj_search_bookName">{{s.bookName}}</h4><br>
                <p class="wj_search_author">{{s.author}}</p>
              </div>
            </li>
          </a>
        </ul>
      </div>

      <div class="wj_search_mask" v-show="wj_search_list">


      </div>

      <div class="wj_index_box01" v-show="wj_index_box01">

        <div class="wj_myshelf" id="wj_myshelf_id">
          <div class="wj_myshelf_title">
            我的书架
            <span>
            <a href="#">
            查看我的书架 >
            </a>
          </span>
          </div>
          <div class="wj_myshelf_list">
            <a href="#" v-for="ms in this.books_myshelf" :key="ms.id">
              <div class="wj_myshelf_item">
                <div class="wj_myshelf_item_img">
                  <img :src="img_myshelf(ms)" alt="图片找不到...">
                </div>
                <p class="wj_myshelf_item_title">{{ms.bookName}}</p>
                <p>{{ms.author}}</p>
              </div>
            </a>
          </div>
        </div>

        <div class="wj_like">
          <div class="wj_like_title">
            猜你喜欢
          </div>
          <div class="wj_like_list">
            <a href="#" v-for="item in this.likeData" :key="item.pic">
              <div class="wj_like_item">
                <div class="wj_like_item_img">
                  <img :src="url_img_computed(item)" alt="图片找不到...">
                </div>
                <p class="wj_like_item_title">{{ item.bookName }}</p>
                <p>{{ item.author }}</p>
              </div>
            </a>
          </div>
        </div>

        <div class="wj_category" id="wj_catdgory_id">
          <div class="wj_category_title">
            分类榜单
          </div>
          <div class="wj_category_list">
            <a href="">
              <div class="wj_category_item">
                <a href="#">
                  <span>精品小说·18374本</span>
                </a>
              </div>

            </a>
            <a href="#">
              <div class="wj_category_item">
                <a href="#">
                  <span>精品小说·18374本</span>
                </a>
              </div>

            </a>
            <a href="#">
              <div class="wj_category_item">
                <a href="#">
                  <span>精品小说·18374本</span>
                </a>
              </div>

            </a>
            <a href="#">
              <div class="wj_category_item">
                <a href="#">
                  <span>精品小说·18374本</span>
                </a>
              </div>

            </a>

            <a href="#">
              <div class="wj_category_item">
                <a href="#">
                  <span>精品小说·18374本</span>
                </a>
              </div>

            </a>
            <a href="#">
              <div class="wj_category_item">
                <a href="#">
                  <span>精品小说·18374本</span>
                </a>
              </div>

            </a>
            <a href="#">
              <div class="wj_category_item">
                <a href="#">
                  <span>精品小说·18374本</span>
                </a>
              </div>

            </a>
            <a href="#">
              <div class="wj_category_item">
                <a href="#">
                  <span>精品小说·18374本</span>
                </a>
              </div>

            </a>

            <a href="#">
              <div class="wj_category_item">
                <a href="#">
                  <span>精品小说·18374本</span>
                </a>
              </div>

            </a>
            <a href="#">
              <div class="wj_category_item">
                <a href="#">
                  <span>精品小说·18374本</span>
                </a>
              </div>

            </a>
            <a href="#">
              <div class="wj_category_item">
                <a href="#">
                  <span>精品小说·18374本</span>
                </a>
              </div>

            </a>
            <a href="#">
              <div class="wj_category_item">
                <a href="#">
                  <span>精品小说·18374本</span>
                </a>
              </div>

            </a>


          </div>
        </div>

      </div>
    </div>

  </div>

</template>

<script>
import axios from 'axios'

export default {
  name: "WJIndex",
  mounted() {

    let username = sessionStorage.getItem('username')

    let password = sessionStorage.getItem('username')

    if (username !== '' && password !== '' && username !== null && password !== null){

      axios({
        'method':'post',
        'url':'http://127.0.0.1:8001/login',
        'data':{
          'username':username,
          'password':password
        }
      }).then(res=>{
        this.books_myshelf = res.data
        console.log('>>>',this.books_myshelf)
      }).catch(err=>{
        console.log('发生错误!!:',err)
      })
    }else {
      let books_default = []
      books_default.push({'id':'111','pic':'111','bookName':'亚丝娜1001','author':'川原砾'})
      books_default.push({'id':'112','pic':'112','bookName':'亚丝娜1002','author':'九里史生'})
      books_default.push({'id':'113','pic':'113','bookName':'亚丝娜1003','author':'Kawahara'})
      books_default.push({'id':'114','pic':'114','bookName':'亚丝娜1004','author':'Reki'})
      this.books_myshelf = books_default
    }

    axios({
      'method': 'get',
      'url': 'http://127.0.0.1:8001/likeData'
    }).then((res) => {
      // console.log('>>',res.data)
      this.likeData = res.data
      // console.log('显示一条:',res.data[0])
    }).catch(res => {
      console.log('>>>出错!!报错信息:', res)
    })

    axios({
      'method': 'get',
      'url': 'http://127.0.0.1:8001/allBooks'
    }).then(res => {
      this.allBooks = res.data
      // console.log('>>>',this.allBooks)
    }).catch(err => {
      console.log('报错!!', err)
    })


  },
  data() {
    return {
      'user': '未登录',
      'url_img': '/img_book/',
      'likeData': [],
      'allBooks': [],
      'wj_index_box01': true,
      'wj_search_list': false,
      'keyword': '',
      'filterBooks': [],
      'img_search':'/img_book/',
      'books_myshelf':[],
      'wj_index_1001':false,
      'wj_login':true,
      'username':'root',
      'password':'root',
      'error_message':''
    }
  },
  methods: {
    wj_register_func(){
      // console.log('>>>',this.username)
      // console.log('>>>',this.password)
      axios({
        headers: {
          'Content-Type': 'application/x-www-form-urlencoded'
        },
        method:'post',
        url:'http://127.0.0.1:8001/userRegister/',
        data:{
          'username':this.username,
          'password':this.password
        },
        'Content-Type': 'application/x-www-form-urlencoded'
      }).then(res=>{
        let info = res.data
        this.error_message = info.error_message
        if (info.status === 'success'){
          this.wj_login = false
          this.wj_index_1001 = true
          this.user = this.username
          // sessionStorage.setItem('username',this.username)
          // sessionStorage.setItem('password',this.password)
        }else{
          alert(this.error_message)
        }
        // console.log('>>',res.data)
      }).catch(err=>{
        console.log(err)
      })
    },
    img_myshelf(ms){
      let img_ms = '/img_book/'+ms.pic+'.jpg'
      return img_ms
    },
    resumeSearch(){
        this.wj_index_box01 = false
        this.wj_search_list = true
    },
    resumeIndex(){
        this.wj_index_box01 = true
        this.wj_search_list = false
    },
    getImgSearch(s){
      let res = this.img_search+s.pic+'.jpg'
      // console.log('>>>',res)
      return res
    },
    getBookByKeyword() {
      this.filterBooks = this.allBooks.filter(b => {
        return b.bookName.indexOf(this.keyword) !== -1 || b.author.indexOf(this.keyword) !== -1
      })
    },
    url_img_computed(item) {
      let res = this.url_img + item.pic + '.jpg'
      // console.log('>>>>',res)
      return res;
    }
  }
}
</script>

<style scoped>
.wj_login{
  width: 500px;
  height: 300px;
  margin: 100px auto;
  background-color: #f5f3f3;
  border-radius: 20px;
  overflow: hidden;
}
.wj_login_table{
  width: 400px;
  height: 300px;
  margin: 40px auto;
  /*background-color: red;*/
  overflow: hidden;
}
.wj_login_table .wj_login_username{
  margin-top: 30px;
  margin-left: 50px;
}
.wj_login_table .wj_login_username input{
  padding-left: 10px;
  height: 40px;
  width: 296px;
  font-weight: bold;
  font-size: 15px;
  border-radius: 8px;
}
.wj_login_table .wj_login_username input:hover{
  box-shadow: 3px 3px 21px 3px #e8e0e0;
}
.wj_login_table .wj_login_password input:hover{
  box-shadow: 3px 3px 21px 3px #e8e0e0;
}
.wj_login_table .wj_login_password{
  margin-top: 30px;
  margin-left: 50px;
}
.wj_login_table .wj_login_password input{
  padding-left: 10px;
  height: 40px;
  width: 296px;
  border-radius: 8px;
  font-weight: bold;
  font-size: 15px;

}
.wj_login .wj_login_button{
  margin-top: 50px;
  margin-left: 50px;
}
.wj_login .wj_login_button button{
  font-weight: bold;
  /*font-size: 20px;*/
  width: 296px;
  height: 40px;
  border-radius: 8px;
  background-color: #4e6ef2;
  opacity: 0.9;
}
.wj_login .wj_login_button button:hover{
  opacity: 1;
  box-shadow: 3px 3px 21px 3px #e8e0e0;
}
.wj_nav_home {
  width: 1519px;
  height: 386px;
  background-color: #edeef0;
}

.wj_search_list {
  width: 320px;
  /*height: 800px;*/
  margin: -300px auto;
  background-color:#ffffff;
  border-radius: 20px;
  overflow: hidden;
}

.wj_search_list ul li div{
  position: relative;
  display: inline-block;
  background-color: #f3f5f8;
  left: 20px;
  bottom: 77px;
}

.wj_search_list li {
  display: block;
  width: 320px;
  height: 217px;
  margin: 20px auto;
  background-color: #f3f5f8;
  list-style: none;
}

.wj_search_list img {
  margin-left: 10px;
  margin-top: 22px;
  width: 40%;
}

.wj_search_mask {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #edeef0;
  z-index: -1;
}

.wj_nav_banner {
  text-align: right;
  width: 1519px;
  height: 72px;
  background-color: #edeef0;
}

.wj_nav_list {
  list-style: none;
  margin-right: 160px;
}

.wj_nav_list li {
  float: right;
  margin-right: 32px;
  line-height: 72px;
}

.wj_nav_list a {
  text-decoration: none;
}

.wj_nav_logo {
  position: relative;
  height: 36px;
  background-color: #edeef0;
  text-align: center;
  line-height: 36px;
  margin-top: 44px;
}

.wj_nav_logo span {
  font-style: normal;
  font-weight: bold;
  font-family: "Lucida Calligraphy", cursive, serif, sans-serif;
  font-size: 20px;
}

.wj_nav_logo img {
  vertical-align: middle;
}

.wj_nav_search {
  width: 700px;
  height: 52px;
  margin: 44px auto;
  border-radius: 26px;
  line-height: 52px;
  /*vertical-align: middle;*/
  background-color: #ffffff;
}

.wj_nav_search input {
  width: 622px;
  height: 41px;
  margin-top: 5px;
  margin-left: 15px;
  border: none;
  outline: none;
  font-size: 17px;
}

.wj_nav_search img {
  margin-top: 0;
  margin-left: 21px;
  vertical-align: middle;
}

.wj_category {
  width: 1520px;
  height: 250px;
  margin-top: 50px;
  margin-bottom: 100px;
  background-color: #f9f9fa;
}

.wj_category_title {
  width: 1200px;
  height: 70px;
  margin: 0 auto;
  font-weight: bold;
  font-size: 17px;
  background-color: #f9f9fa;
  line-height: 70px;
}

.wj_category_list {
  width: 1200px;
  height: 182px;
  background-color: #f9f9fa;
  margin: 0 auto;
  overflow: hidden;
}

.wj_category_item {
  float: left;
  width: 300px;
  height: 60px;
  line-height: 60px;
  /*padding-left: 20px;*/
  background-color: #f9f9fa;
}

.wj_category_item span {
  margin-left: 20px;
}

.wj_category_item:hover {
  transition: 0.3s;
  background-color: #ebf3fa;
}

.wj_category_item a {
  text-decoration: none;
}

.wj_like {
  width: 1520px;
  height: 450px;
  margin-top: -30px;
  background-color: #f9f9fa;
}

.wj_like_title {
  width: 1200px;
  height: 70px;
  margin: 0 auto;
  line-height: 70px;
  font-weight: bold;
  font-size: 17px;
  background-color: #f9f9fa;
}

.wj_like_list {
  width: 1224px;
  height: 352px;
  margin: 0 auto;
  background-color: #f9f9fa;
}

.wj_like_item_img {
  width: 50%;
  margin: 30px auto;
}

.wj_like_item_img img {
  width: 100%;
}

.wj_like_item_title {
  font-weight: bold;
  font-size: 17px;
  margin-bottom: 20px;
}

.wj_like_list p {
  text-align: center;
}

/*.wj_like_item_01 {*/
/*  float: left;*/
/*  width: 282px;*/
/*  height: 352px;*/
/*  background-color: #ffffff;*/
/*  box-shadow: 2px 2px 16px 2px #c3b6b6;*/
/*}*/

.wj_like_item_01:hover {
  transform: scale(1.1);
  transition: 0.8s;
}

.wj_like_item {
  float: left;
  margin-left: 24px;
  width: 282px;
  height: 352px;
  background-color: #ffffff;
  box-shadow: 2px 2px 16px 2px #c3b6b6;
}

.wj_like_item:hover {
  transition: 0.8s;
  transform: scale(1.1);
}

/*书架*/

.wj_myshelf {
  width: 1520px;
  height: 450px;
  margin-top: -30px;
  background-color: #f9f9fa;
}

.wj_myshelf_title {
  width: 1200px;
  height: 70px;
  margin: 0 auto;
  line-height: 70px;
  font-weight: bold;
  font-size: 17px;
  background-color: #f9f9fa;
}

.wj_myshelf_title span {
  display: block;
  float: right;
  font-weight: bold;
  font-size: 17px;
  margin-right: 10px;
  opacity: 0.7;
}

.wj_myshelf_title span:hover {
  opacity: 1;
}

.wj_myshelf_title a {
  text-decoration: none;
}

.wj_myshelf_list {
  width: 1224px;
  height: 352px;
  /*height: 452px;*/
  margin: 0 auto;
  background-color: #f9f9fa;
}

.wj_myshelf_item_img {
  width: 50%;
  margin: 30px auto;
}

.wj_myshelf_item_img img {
  width: 100%;
}

.wj_myshelf_item_title {
  font-weight: bold;
  font-size: 17px;
  margin-bottom: 20px;
}

.wj_myshelf_list p {
  text-align: center;
}

.wj_myshelf_item_01 {
  float: left;
  width: 282px;
  height: 352px;
  background-color: #ffffff;
  box-shadow: 2px 2px 16px 2px #c3b6b6;

}

.wj_myshelf_item_01:hover {
  transition: 0.8s;
  transform: scale(1.1);
}

.wj_myshelf_item {
  float: left;
  margin-left: 24px;
  width: 282px;
  height: 352px;
  background-color: #ffffff;
  box-shadow: 2px 2px 16px 2px #c3b6b6;
}

.wj_myshelf_item:hover {
  transition: 0.8s;
  transform: scale(1.1);
  /*background-color: aqua;*/
}
</style>
