## X-Tag

### X-Tag是什么
X-Tag 是一个微软支持的开源的 JavaScript 库, 它包装了 W3C 标准 Web 组件系列的 api, 为快速组件开发提供了一个紧凑、功能丰富的界面。虽然 X-Tag 为所有 Web 组件 api (Custom Elements、Shadow DOM、 Templates和 HTML Imports) 提供了功能钩子, 但它只需要自定义元素支持才能操作。在没有本地自定义元素支持的情况下, X-Tag 使用了 Google 的 Polymer 框架 polyfills。

### 浏览器支持
    Edge (all versions and devices), Internet Explorer 9+
    Firefox (all versions, devices, and platforms)
    Chrome (all versions, devices, and platforms), Android 4+ stock browser
    Safari Mac, Safari iOS 5+
    Opera 11+ (all devices and platforms)

### 示例
这里有一个很棒的<x-click>组件，帮助您了解使用X-Tag创建Web组件的方式。正如您所看到的，有一个 tap 事件附加到元素上，让您开始和停止时间.

    xtag.register('x-clock', {
      lifecycle: {
        created: function(){
          this.start();
        }
      },
      methods: {
        start: function(){
          this.update();
          this.xtag.interval = setInterval(this.update.bind(this), 1000);
        },
        stop: function(){
          this.xtag.interval = clearInterval(this.xtag.interval);
        },
        update: function(){
          this.textContent = new Date().toLocaleTimeString();
        }
      },
      events: {
        tap: function(){
          if (this.xtag.interval) this.stop();
          else this.start();
        }
      }
    });

### 相关文档
    http://x-tag.github.io/ 
    https://x-tag.readme.io/ 