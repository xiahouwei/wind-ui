# wind-ui/风行UI

> Mobile UI elements for **Vue 2.0**

<!-- - [Homepage](https://xiahouwei.github.io/home) -->
<!-- - [Documentation](http://xiahouwei.github.io/docs) -->


## Installation/安装

```shell
npm install wind-ui -S

```


## Usage/使用

Import all components.

```javascript
import Vue from 'vue';
import WindUI from 'wind-ui';

Vue.use(WindUI);
```

##组件


####弹窗组件

####1.Loading 加载
```
 * @param {text} [str] - 显示在下方的文本信息
 * @param {loadingType}  [str] - loading动画样式
 *
 * @event {on-show} 显示时触发
 * @event {on-hide} 隐藏时触发
 *
 * @plugin 开启 vue.$WLoading('text').then() 或 vue.$WLoading({}).then()
 * @plugin 关闭 vue.$WAlert.end().then()
 * 
 * @then(arg) 
 * arg 开启或关闭Loading组件的回调
 * 
 * @example
 * <w-loading v-model="show"></w-loading>
 * 或
 * this.$Wloading('加载中...')
 *
 * 改变loading动画
 * loadingType:'动画名称' (可选:light,flower,peas)
 * this.$WLoading({
 *   text:'加载中...',
 *   loadingType:'flower'
 * })
```
####2.LoadingType 加载动画
```
 * @desc Loading加载动画
 * @param {type} [str] - 动画类型
 * @param {size}  [str] - 尺寸
 *
 * @example
 * <w-loadingType type='light'></w-loadingType>
 * 
 * <w-loadingType type='1'></w-loadingType>
 *
 * <w-loadingType size="60"></w-loadingType>
 *
```
####3.Toast 提示框
```
 * @param {message} [str] - 显示在下方的文本信息
 * @param {duration}  [nub] - 提示框显示时间
 * @param {iconClass}  [str] - 提示框自定义图标
 * @param {position}  [str] - 提示框位置 可选[top,bottom,middle]
 * @param {type}  [str] - 提示框内置样式对应的类型 可选[success,warning,cancel,text]
 * @param {width}  [String,Number] - 提示框宽度(如果用str需要加上px,或百分号)
 * @param {maskShow}  [str] - 是否显示遮罩层
 *
 * @event {on-show} 显示时触发
 * @event {on-hide} 隐藏时触发
 *
 * @plugin 开启 vue.$WToast({}).then()
 * 
 * @then(arg) 
 * arg 关闭Toast组件的回调
 * 
 * @example
 * <w-toast v-model="show"></w-toast>
 * 提示框消失 自动 $emit  value:false, 绑定v-model 即可双向绑定
 * 或
 * this.$WToast({
 *   message: 'middle提示',
 *   position: 'middle',
 *   type: 'warning',
 * })
```
####4.Dialog显示
```
 * @param {value} [boolean] - 显示/关闭  支持双向绑定
 * @param {clickMaskHide} [boolean] - 点击遮罩层关闭
 *
 * @event {on-show} 显示时触发
 * @event {on-hide} 隐藏时触发
 * @event {on-mask} 点击遮罩隐藏时触发
 * 
 * @example
 * <w-dialog v-model="show"></w-dialog>
```

####5.confirm提示框
```
 * @param {value} [str] - 是否显示,用 v-model 绑定
 * @param {title}  [str] - 提示标题
 * @param {message}  [str] - 提示内容
 * @param {btnConfirmText}  [str] - confirm按钮内容
 * @param {btnCancelText}  [str] - cancel按钮内容
 * @param {titleColor}  [str] - 标题字体颜色
 * @param {messageColor}  [str] - 内容字体颜色
 * @param {clickMaskHide}  [boolean] - 是否开启点击遮罩关闭
 *
 * @event {on-show} 显示时触发
 * @event {on-hide} 隐藏时触发
 * @event {on-confirm} 点击confirma按钮时触发
 * @event {on-cancel} 点击cancel按钮时触发
 * @event {on-mask} 点击遮罩时触发
 *
 * @plugin 开启 vue.$WConfirm({})
 * @plugin 关闭 vue.$WConfirm.close()
 * 
 * @then(arg1,arg2) 
 * arg1 插件调用的时候,点击confirm按钮触发的回调
 * arg2 插件调用的时候,点击cancel按钮和遮罩触发的回调
 * 
 * @example
 * <w-confirm v-model="show"></w-confirm>
 * 或
 * this.$WConfrim('这是一个提示')
 * 或
 * this.$WConfrim({
 *   title: '你好',
 *   message: '请做一个选择'
 *   clickMaskHide: true
 * }).then(() => {
 *   console.log('这是confirm的回调')
 *   this.switchValue11 = false
 * }, () => {
 *   console.log('这是cancel的回调')
 *    this.switchValue11 = false
 * })
```

####6.alert提示框
```
 * @param {value} [str] - 是否显示,用 v-model 绑定
 * @param {title}  [str] - 提示标题
 * @param {message}  [str] - 提示内容
 * @param {btnConfirmText}  [str] - confirm按钮内容
 * @param {titleColor}  [str] - 标题字体颜色
 * @param {messageColor}  [str] - 内容字体颜色
 * @param {clickMaskHide}  [boolean] - 是否开启点击遮罩关闭
 *
 * @event {on-show} 显示时触发
 * @event {on-hide} 隐藏时触发
 * @event {on-confirm} 点击确定按钮关闭时触发
 * @event {on-mask} 点击遮罩时触发
 * 
 * @plugin 开启 vue.$WAlert({})
 * @plugin 关闭 vue.$WAlert.close()
 * 
 * @then(arg1) 
 * arg1 插件调用的时候,点击confirm按钮和遮罩 都会触发then()内的回调
 * 
 * @example
 * <w-alert v-model="show"></w-alert>
 * 或
 * this.$WAlert('这是一个提示')
 * 或
 * this.$WAlert({
 *   title: '你好',
 *   message: '这是一个提示'
 *   clickMaskHide: true
 * }).then(() => {
 *   console.log('alert回调')
 *   this.switchValue13 = false
 * })
```
####7.actionSheet提示框
```
 * @desc actionSheet 提示框
 * @param {value} [boolean] - 显示/关闭  支持双向绑定
 * @param {title} [String] - 提示框标题
 * @param {menus} [Object, Array] - 菜单
 * @param {showCancel} [Boolean] - 显示cancel按钮
 * @param {cancelText} [String] - cancel按钮内容
 * @param {clickMaskHide} [Boolean] - 点击遮罩关闭
 * 
 * @event {on-menu} 点击菜单触发(menu没有value)
 * @event {on-menu-${menuvalu}} 点击菜单触发(menu有value)
 * @event {on-mask} 点击遮罩触发
 * @event {on-cancel} 点击取消按鈕触发
 *
 * @example
 * <w-actionSheet v-model="switchValue14" title="这是一个提示" :menus="menus" v-on:on-cancel="onCancel"></w-actionsheet>
 * menus: [
        {
            label: '确定',
            type: 'primary',
            value: 'confirm'
            clickMenuHide: false
        },
        {
            label: 'warning',
            type: 'warning',
            value: 'warning'
        },
        {
            label: 'disabled',
            type: 'disabled',
            value: 'disabled'
        },
        {
            label: '<span style="color:blue;">Default+自定义</span>'
        }
    ]
```
####8.popup 弹出框
```
 * @param {value} [boolean] - 显示/关闭  支持双向绑定
 * @param {showMask} [boolean] - 显示/关闭  遮罩
 * @param {clickMaskHide} [Boolean] - 点击遮罩关闭
 * @param {position} [string] - 定位 可选 top,bottom,left,right
 * @param {popupStyle} [Object] - 主体窗口样式
 * @param {height} [string] - 高度, position为 top,bottom,或空 时有效(如果用str需要加上px,或百分号)
 * @param {width} [string] - 宽度, position为 left,right,或空 时有效(如果用str需要加上px,或百分号)
 * @param {isTransparent} [Boolean] - 主体窗口透明
 * @param {maxHeight} [string] - 最大高度
 *
 * @event {on-show} 显示时触发
 * @event {on-hide} 隐藏时触发
 *
 * @example
 * <w-popup v-model="switchValue15" :clickMaskHide="true" position='top' :show-mask='true' width="50%" height="50%" maxHeight="50%">
 * <div>显示文本</div>
 * <div>显示文本</div>
 * </w-popup>
 ```
####表单组件

####1.Switch 开关
```
 * @desc 切换按钮
 * @param {value} [boolean] - 绑定值，支持双向绑定
 * @param {slot}  [str] - 显示内容
 * @param {disabled} [slot] - 是否禁用
 *
 * @example
 * <w-switch v-model="value"></w-switch>
 * 1.一般使用绑定value即可实现双向绑定
 * 2.如有权限需求 绑定 disabled 即可
 * 3.需要根据开启/关闭 执行函数 绑定change 即可
 ```
###2.Button 按钮
```
 * @param {type} [str] - 按钮样式类型 默认default 可选[default,primary,warn]
 * @param {disabled}  [boolean] - 禁用
 * @param {mini}  [boolean] - 小尺寸
 * @param {plain}  [boolean] - 镂空按钮
 * @param {text}  [str] - 按钮文本
 * @param {actionType}  [str] - 按钮类型 可选[button submit reset]
 * @param {showLoading}  [boolean] - 显示loading图标
 * @param {link}  [String] - 跳转的链接
 *
 * @event {click} 点击触发
 * 
 * @example
 *  <w-button type='primary' :disabled="false" :plain="false" :mini="false" :showLoading="false" @click='buttonClick'>确定</w-button>
 *  <w-button type='warn' :disabled="false" :plain="true" :mini="true">取消</w-button>
```
###3.Tabbar 底部切换标签
```
 * @desc 底部tabbar标签
 * @param {value} [Number] - 选中的子元素
 * @param {iconClass}  [String] - 图标样式
 * 
 * @slot {label} tabbar选项名称
 * 
 * @event {on-index-change} arg[val, oldVal]  点击触发(发送当前选中子元素索引,原子元素索引)
 *
 * @desc 底部tabbar-item 标签选项
 * @param {showDot} [boolean] - 待处理红点
 * @param {disabled}  [boolean] - 禁用
 * @param {iconClass}  [String] - 图标样式
 * @param {selected}  [boolean] - 选中
 *
 * @slot {icon}  tabbar选项图标
 * @slot {icon-active} tabbar选项图标选中状态
 *
 * @event {on-item-click} arg[currentIndex]  点击触发(发送当前标签索引)
 * 
 * @example
  <w-tabbar>
    <w-tabbar-item :selected='true' @on-item-click="itemClick">
      <img slot="icon" src="../assets/micOff.png">
      <img slot="icon-active" src="../assets/micOn.png">
      <span slot="label">News</span>
    </w-tabbar-item>
    <w-tabbar-item :showDot='true' @on-item-click="itemClick">
      <img slot="icon" src="../assets/micOff.png">
      <img slot="icon-active" src="../assets/micOn.png">
      <span slot="label">News</span>
    </w-tabbar-item>
  </w-tabbar>
```
###4.Header 顶部标题栏
```
 * @param {title}  [String] - 标题文本
 * @param {transitionName}  [String] - 切换路由页面动画效果名称
 * @param {leftOptions}  [Object] - 左侧设置
 * @param {leftOptions.showBackBtn}  [Boolean] - 显示左侧后退按钮
 * @param {leftOptions.leftBackText}  [String] - 左侧按钮文字
 * @param {leftOptions.preventGoBack}  [Boolean] - 左侧后退按钮是否阻止返回
 * @param {rightOptions}  [Object] - 右侧设置
 * @param {rightOptions.showMore}  [Boolean] - 是否显示右侧更多按钮
 * 
 * @event {on-click-back} 当阻止返回时 点击左侧后退按钮触发
 * @event {on-click-title} 点击标题触发
 * @event {on-click-more} 点击右侧更多按钮触发
 * 
 * @example
 *  <w-header :leftOptions="leftOptions" :rightOptions="rightOptions">
        这是标题显示不开会显示...
        <span slot="header-right">更多</span>
    </w-header>
    leftOptions: {
        showBackBtn: true,
        preventGoBack: false,
        leftBackText: '返回去'
    },
    rightOptions: {
        showMore: true
    }
```
###5.Cell 单元格
```
 * @param {title}  [String] - 标题文本
 * @param {label}  [String] - 标题备注信息
 * @param {value}  [String] - 右侧显示文字
 * @param {isLink}  [Boolean] - 显示右侧箭头
 * @param {link}  [String] - 跳转的链接
 * 
 * @slot {cell-title}  - 同 title, 会覆盖 title 属性
 * @slot {cell-icon}  - 左侧icon插槽
 * @slot {cell-value}  - 同 value, 不会覆盖 value 属性
 *
 * @example
 *<w-cell title="Live Demo" @click.native="liveDemoCellClick" link="/helloWorld">
    <img slot="cell-icon" class="cell-icon" src="../assets/demo.png"></img>
  </w-cell>
 */
```
###6.Index-list 索引列表
```
 * @desc index-list : cell group of index
 * @param {height} [Number] - custom height (cover bottom,haveTabbar)
 * @param {showIndexToast}  [Boolean] - show index toast
 * @param {haveTabbar}  [Boolean] - subtracted  value of tabbar(53) by height
 * @param {bottom}  [Number] - subtracted custom value by height (cover haveTabbar)
 *
 * @desc index-list-item
 * @desc index-list-item 标签选项
 * @param {index} [String] - index(must)
```
###7.swipe 轮播图
```
 * @desc swipe : loop image
 * @param {height} [Number] - custom height (default 100%)自定义高度
 * @param {defaultIndex}  [Number] - default display of the image index 默认显示索引
 * @param {showIndexDot}  [Boolean] - Whether show indexdot 显示索引点
 * @param {loop}  [Boolean] - Whether loop 是否循环滚动
 * @param {speed}  [Number] - img animation time 滚动速度
 * @param {interval}  [Number] - img loop display interval 滚动间隔
 * @param {prevent}  [Boolean] - blocking browser default events 浏览器默认行为
 * @param {stopPropagation}  [Boolean] - stopPropagation 阻止冒泡
 * 
 * swipe-item
 * @param {lineHeight} [Number] - loop image item lineHeight (default father height value)
 * 子组件高度
 *
 * @event {on-index-change} arg[val, oldVal]  img change emit(emit newIndex, oldIndex)
 * @event {on-item-click} arg[currentIndex]  img-item click emit(emit currentIndex)
```
## developer/开发者

Shang HuaWei/商华伟

Tianjin Fengxing science and Technology Information Engineering Co., Ltd.

天津市风行科技信息工程有限公司

