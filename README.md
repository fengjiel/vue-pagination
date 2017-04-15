# vue-pagination
之前一直用layerPage做分页插件的 但是转vue后用layer总感觉怪怪的，所以仿照layer写了个vue组件
使用方法：
```
js
import pagination from '../../components/vue-pagination' //引入分页组件
export default {
    components: {
      pagination,    //注册组件
    },
    data() {
       return {
          total: 30,     // 记录总条数   默认空，如果小于pageNum则组件不显示   类型Number
          pageNum: 10,    // 每页显示条数,默认10                              类型Number
          current: 1,     // 当前页数，   默认为1                             类型Number
          pagegroup:5     // 分页条数     默认为5，需传入奇数                  类型Number
          skin:'#16a086'  // 选中页码的颜色主题 默认为'#16a086'                类型String
         }
    },
     methods:{
        pagechange:function(current){     // 页码改变传入新的页码，此处做回调
           console.log(current);
        }
    }
}

html

<pagination 
    :total="total" 
    :current="current" 
    :skin="skin" 
    :pagenum="pageNum" 
    :pagegroup="pagegroup" 
    @change="pagechange"
    ></pagination>
```
默认样式如下
![avatar](https://raw.githubusercontent.com/fengjiel/vue-pagination/master/WX20170415-143027%402x.png)
