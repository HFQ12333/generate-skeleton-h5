# generate-skeleton-h5
自动生成h5骨架屏

## 安装骨架屏插件
```javascript
npm i draw-page-structure -D
```

## 页面引入
```javascript
import { generateSkeleton } from "generate-skeleton-h5"
generateSkeleton().then(res => {
  // 当前页面的骨架屏代码，含html与css
  console.log(res)
})
```

## 使用注意事项
1、使用变量控制骨架屏显示隐藏，通常将其初始值设为 true，在接口调用后改为 false，建议加入 try catch，防止接口报错后页面一直是骨架屏
2、在骨架屏显示期间如果页面不止一屏，骨架屏div元素上加 @touchmove.prevent能阻止页面滑动
3、由于骨架屏的位置是绝对定位，页面滚动后返回如果不是在顶部可能会出现骨架屏没有覆盖页面的情况，使用window.scrollTo(0,0)置顶，或者控制不再加载骨架屏