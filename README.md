# uniapp-modal

几种常用类型，自定义modal，覆盖原生导航栏

## 使用方式

**在main.js中**  

~~~
// 注册全局modal组件
import chunLeiModal from '@/components/chunLei-modal/chunLei-modal.vue'
Vue.component('chunLei-modal',chunLeiModal);
~~~

**在index.vue中**  

~~~
<template>
  <view class="content">
    <chunLei-modal v-model="value" :mData="data" :type="type" @onConfirm="onConfirm" @onCancel="onCancel" navMask>
    </chunLei-modal>
  </view>
</template>
~~~

## OBJECT参数说明

| 参数 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| type | String | default | modal类型：default，select，advert，share，input，custom |
| value | Boolean | false | 是否显示 |
| maskEnable | Boolean | true | 是否点击遮罩退出 |
| mData | Object, Array | Object | 数据 |
| navMask | Boolean | 否 | 是否遮住原生导航栏(顶部和tabbar) |
| nav | Boolean | true | 该页面是否有原生顶部导航栏。true遮住顶部和tabbar，false遮住底部 |

**mData数据示例**  

~~~
defaultData:{title:'提示',content:'这是一个模态弹窗',cancelText:'cancel',confirmColor:'#3CC51F'},
selectData:[{title:'拍摄',content:'照片或视频',icon:'../../static/shoot.png'},{title:'从照片选择'}],
advertData:{src:'../../static/advert.jpg',width:'600rpx',height:'350rpx'},
shareData:[
  {title:'朋友圈',icon:'../../static/pengyouquan.png'},
  {title:'微信好友',icon:'../../static/weixinhaoyou.png'},
  {title:'微博',icon:'../../static/weibo.png'},
  {title:'QQ好友',icon:'../../static/QQhaoyou.png'},
  {title:'QQ空间',icon:'../../static/QQkongjian.png'}
 ],
inputData:{
  title:'登录',
  content:[
  {title:'手机号',content:'',type:'number',placeholder:'请输入手机号'},
  {title:'密码',content:'',type:'password',placeholder:'请输入密码'}
  ]
}
~~~

## 事件

| 事件名 | 说明 |
| ---  | --- |
| onConfirm | 用户点击了确定按钮 |
| onCancel | 用户点击了取消按钮 |

如果觉得插件不错，麻烦给个Star [gitHub](https://github.com/15157757001/uniapp-modal)
