# Frontend Mentor - Article preview component solution

This is a solution to the [Article preview component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/article-preview-component-dYBN_pYFT). ![Design preview for the Article preview component coding challenge](./design/desktop-preview.jpg)

## Table of contents

- [Frontend Mentor - Article preview component solution](#frontend-mentor---article-preview-component-solution)
  - [Table of contents](#table-of-contents)
  - [Overview](#overview)
    - [The challenge](#the-challenge)
  - [My process](#my-process)
    - [Built with](#built-with)
    - [What I learned](#what-i-learned)
    - [Useful resources](#useful-resources)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the component depending on their device's screen size
- See the social media share links when they click the share icon

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow

### What I learned

1. 让元素水平垂直居中: 绝对定位 + translate

   ```html
   <div class="father">
     <div class="son">子元素的内容</div>
   </div>
   ```

   ```css
   .father {
     position: relative;
   }
   .son {
     position: absolute;
     top: 50%;
     left: 50%;
     transform: translate(-50%, -50%);
   }
   ```

2. CSS 三角形

   内容为空，四周的 border 均为三角形，设置其他三边颜色为透明，可形成不同方向的小三角形
   border 大小决定三角形大小

   ```css
   .share-list::after {
     content: "";
     position: absolute;
     bottom: -20px;
     left: 100px;
     border: 1em solid;
     border-color: var(--dark-grayish-blue) transparent transparent;
   }
   ```

3. toggle-menu

   [简化版](https://codepen.io/effycoco/pen/VwMWZOw?editors=1111)
   完整版见 CSS in Depth 8.1.1

4. 利用 flexbox 实现一中一下布局[codepen](https://codepen.io/effycoco/pen/GRMEOgZ)
5. 对于纯装饰性的内容如图标应使用 aria-hidden="true"
   aria-label 属性用来给当前元素加上的标签描述，接受字符串作为参数。是用不可视的方式给元素加 label
   例如用于分享的社交网站列表应这样写：

   ```html
   <ul>
     <li>
       <a aria-label="github"><svg aira-hidden="true"></svg></a>
     </li>
     <li>
       <a aria-label="twitter"><svg aira-hidden="true"></svg></a>
     </li>
     <li>
       <a aria-label="codewars"><svg aira-hidden="true"></svg></a>
     </li>
   </ul>
   ```

6. 控制下拉菜单是否显示的按钮应该加上`aira-expanded="false"`

### Useful resources

- [CSS in Depth 7.3.2 制作 css 三角形](https://www.example.com) - 介绍了原理和用法.
- [CSS in Depth 8.1.1](https://www.example.com) - 介绍了通过按钮控制菜单开关的方法.
