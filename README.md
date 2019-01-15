## 小程序生成图片库[Painter]的Wepy版本

## 基于[painter-wepy](https://github.com/hjyue1/painter-wepy)同步[Painter]新特性

### 安装
```bash
    npm install wepy-painter --save
```
```bash
    import painter from 'wepy-painter'
```
### 例子
```bash

<script>
    <template lang="wxml" minapp="wepy">
        <painter :palette.sync="palette" @imgOK.user="onImgOK" />
    </template>
</script>

import wepy from 'wepy'
import painter from 'wepy-painter'

export default class Index extends wepy.page {
    components = {
        painter
    }
    data = {
        palette: {
            {
                width: '654rpx',
                height: '1000rpx',
                background: '#eee'
                views: [
                    {
                        type: 'text',
                        text: 'borderWidth',
                        css: {
                            bottom: '40rpx',
                            right: '200rpx',
                            color: 'green',
                            borderWidth: '2rpx'
                        }
                    }
                ]
            }
        }
    }
    methods = {
        onImgOK(e) {
            this.imgUrl = e.path
            this.$apply()
        }
    }
}
```
### 更多详细文档，参阅[Painter]

[Painter]: https://github.com/Kujiale-Mobile/Painter