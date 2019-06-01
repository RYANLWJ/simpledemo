# Build a simple Accordion menu with Vue.js
> Hey ,guys , great to meet you here ! This is a very simple accordion menu demo built with vue.js .Hopefully, it will give you some help! 
  
 **** 

### css part
  
 ```
     #wrap {
        width: 250px;
        margin: 100px auto;
        color: white;
        text-align: center;
        border-radius: 6px;
        overflow: hidden;
    }
    
    .title {
        width: 100%;
        line-height: 30px;
        cursor: pointer;
        border-bottom: 1px solid #ddd;
    }
    .title:nth-last-child(1){
        border-bottom: none;
    }

    .tt {
        background-color: tomato;
    }

    .fade-enter-active{
        height:30px;
        transition: height 0.5s linear;
    }
     
    .fade-enter{
        height: 0;
    }
    .item{
        color:black;
        cursor: pointer;
        overflow: hidden;
    }
    
    .item:hover{
        background-color: rgb(250, 155, 138);
        color:rgb(255, 255, 255);
    }
```

### html part 

```
    <div id="wrap">
        <ul class="title" v-for="(values,idx) in origin">
            <li @click="ctrlShow(idx)" class="tt" v-text="values.title"></li>
            <transition-group name="fade" tag="ul" class="con_wrap">
                <li v-if="idx==mark&&isOk" class="cons" v-for="item in values.content "  :key="idx">
                    <a class="item" href="###" v-text="item"></a>
                </li>
            </transition-group>
        </ul>
    </div>
```

### js part   

```
        <script>
        let vm = new Vue({
            el: '#wrap',
            data: {
                origin: [{
                        title: '最新资讯',
                        content: [
                            '黑洞理论得到证实',
                            '部分名企员工承认996的存在'
                        ]
                    },
                    {
                        title: '今日头条',
                        content: [
                            '广州今天阳光明媚',
                            '香港人均收入再创新低',
                            '北京下雪了'
                        ]
                    },
                    {
                        title: '深度好文',
                        content: [
                            '何为伪中产',
                            '如何让自己不那么浮躁'
                        ]
                    }
                ],
                mark: -1,
                isOk: true
            },
            methods: {
                ctrlShow(currIdx) {
                    // console.log(currIdx,this.mark)
                    // console.log(this.isOk, '<---')
                    if (currIdx == this.mark && this.isOk) {
                        this.isOk = !this.isOk;
                        return;
                    } else if (currIdx == this.mark) {
                        this.isOk = !this.isOk;
                        return;
                    }
                    this.mark = currIdx;
                    this.isOk = true;
                }
            }
        })
    </script>
```

****
##### RYAN LI
  ###### Any questions,please feel free to contact me. 
  essentialmomo@icloud.com
  ###### Have a good day !
