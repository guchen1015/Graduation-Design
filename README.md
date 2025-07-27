项目概述
这是一个融合了故障艺术、动态交互和现代UI设计的毕业设计展示网站。项目采用深蓝渐变背景营造科技感，结合三种核心交互体验：故障文字效果、动态卡片堆叠和现代化联系表单。

核心技术栈
HTML5 & CSS3（渐变、动画、Flexbox布局）

JavaScript（交互动效实现）

Font Awesome（图标库）

响应式设计（适配移动端）

核心功能与交互体验
1. 故障文字艺术效果
javascript
// 实现故障文字效果的核心代码
const faulttext = {
  fault() {
    this.texts.forEach((text) => {
      text.classList.add("faulttext_fault");
      text.style.transform = `translate(${Math.random()*60-30}%,${Math.random()*60-30}%)`;
      // 随机裁剪路径创造故障效果
      text.style.clipPath = `polygon(${x}% ${y}%, ${x+w}% ${y}%, ...)`
    })
  }
}
点击"GRADUATION"文字触发随机位移和裁剪效果

使用CSS伪元素和mix-blend-mode创建颜色分离效果

30ms间隔的定时器产生持续故障动画

2. 动态卡片堆叠
css
/* 卡片基础样式 */
.poker {
  position: absolute;
  width: 20rem;
  height: 26rem;
  border-radius: 1.5rem;
  background: linear-gradient(135deg, #0066cc, #4da6ff);
  transform-origin: bottom left;
  box-shadow: 0 10px 30px rgba(0,30,60,0.5);
}

/* 卡片层级设置 */
.poker1 { transform: rotate(-10deg); }
.poker2 { transform: rotate(-6deg) translate(35%, -12%); }
/* ...更多卡片位置 */
javascript
// 卡片点击交互逻辑
const poker = {
  move() {
    this.poker_eles.map((ele) => {
      if(ele.nums+1 >= this.poker_eles.length) {
        // 循环到顶部时更换卡片颜色
        colorBlock.style.background = this.colors[this.card_index];
        this.card_index++;
      }
      // 更新卡片位置
      ele.style.transform = this.transform_datas[nums];
    });
  }
}
5张卡片以不同角度堆叠展示

点击顶部卡片触发循环动画

10种预设渐变色彩循环切换

流畅的transform过渡动画

3. 现代化联系表单
html
<div class="contact-form">
  <form id="contactForm">
    <div class="form-group">
      <label for="name">你的称呼 / YOUR NAME</label>
      <input type="text" id="name" name="name" required placeholder="请输入您的姓名">
    </div>
    <!-- 更多表单字段 -->
    <button type="submit" class="submit-btn">SUBMIT</button>
  </form>
</div>
磨砂玻璃效果的表单背景（backdrop-filter）

渐变色提交按钮带动画效果

三种联系方式卡片（邮箱、QQ、微信）

GitHub项目卡片带悬浮效果

表单提交前端验证与反馈

设计亮点
视觉设计
深空蓝渐变背景：background: linear-gradient(135deg, #000d1a, #001a33, #001220)

动态光点装饰：随机生成的发光点浮动动画

霓虹文字效果：background-clip: text实现的渐变文字

磨砂玻璃效果：backdrop-filter: blur(10px)

交互细节
导航栏滚动变色效果

滚动指示器动画

联系卡片悬停特效

响应式布局适配移动端

部署与使用
直接打开HTML文件即可运行

需要网络连接加载Font Awesome

所有交互功能无需后端支持

图表
代码
graph TD
    A[首页] --> B[故障文字效果]
    A --> C[卡片交互]
    A --> D[联系表单]
    B --> E[点击触发故障动画]
    C --> F[点击卡片切换颜色]
    D --> G[表单提交]
    D --> H[联系方式展示]
灵感来源
设计灵感来源于故障艺术(Glitch Art)和现代UI设计趋势，特别参考了http://www.jiejoe.com的设计风格。

响应式设计
桌面端：完整展示所有效果

平板：缩放卡片尺寸

手机端：垂直排列导航项，简化布局

项目结构
text
index.html
├── CSS样式（内联）
│   ├── 全局样式
│   ├── 导航栏
│   ├── 内容区域
│   ├── 故障文字效果
│   ├── 卡片堆叠效果
│   ├── 联系表单
│   └── 响应式适配
├── JavaScript（内联）
│   ├── 故障文字动画
│   ├── 卡片交互逻辑
│   ├── 动态光点生成
│   ├── 表单处理
│   └── 滚动监听
└── 外部依赖
    └── Font Awesome图标库
