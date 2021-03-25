<template>
    <div id="SecondComponent">
        <h1>I am another page</h1>
        <el-card class="box-card">
            <div slot="header" class="clearfix">
                <h1 style="line-height: 36px; color: #20A0FF">Try "Yes Or No"</h1>
                <button @click="getAnswer">碰碰运气</button>
            </div>
            <div v-for="article in articles" class="text item">
                {{article.title}}
            </div>
        </el-card>

    </div>
</template>

<script>
    export default {
        data() {
            return {
                articles: [],
            }
        },
        created: function () {
            this.getAnswer = this._.debounce(this.yesOrNo, 1000);
        },
        mounted: function () {
            /*this.$http.jsonp('https://api.douban.com/v2/movie/top250?count=10', {}, {
                headers: {

                },
                emulateJSON: true
            }).then(function(response) {
              // 这里是处理正确的回调

                this.articles = response.data.subjects

            }, function(response) {
                // 这里是处理错误的回调
                console.log(response)
            });*/
            this.yesOrNo();
        },
        methods: {
            yesOrNo: function () {
                let vm = this;
                this.axios.get('https://yesno.wtf/api')
                    .then(function (response) {
                        vm.articles.push({'title': response.data.answer});
                    })
                    .catch(function (error) {
                        vm.articles.push({'title': 'Error! Could not reach the API. ' + error});
                    })
            },
            getAnswer: function() {

            }
        }
    }
</script>

<style>

</style>
