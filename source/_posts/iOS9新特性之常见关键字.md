---
uuid: e712da96-76ed-11e9-b6f1-ff1747528169
title: iOS9新特性之常见关键字
date: 2017-09-15 09:59:55
updated:
categories:
    - iOS
tags:
    - iOS9新特性
---
---

> 文章摘要：介绍iOS9常见关键字的作用

<!-- more -->
***
<!-- 内容 -->
- iOS9新出的关键字是用来修饰属性、方法的参数和返回值
- 目的是迎合Swift，提高开发人员的代码规范，减少程序员之间的交流
- iOS新出的关键字有* nonnull、 nullable、 null_resettable、 _Null_unspecified *，只能修饰对象，不能修饰基本数据类型
{% codeblock nullable表示可为空 lang:objc %}
 // nullable书写规范:
 // 方式一:
 @property (nonatomic, strong, nullable) NSString *name;
 // 方式二:
 @property (nonatomic, strong) NSString *_Nullable name;
 // 方式三:
 @property (nonatomic, strong) NSString *__nullable name;
{% endcodeblock %}
{% codeblock nonnull表示不能为空 lang:objc %}
 // nonnull书写规范:
 // 方式一:
 @property (nonatomic, strong, nonnull) NSString *name;
 // 方式二:
 @property (nonatomic, strong) NSString *_Nonnull name;
 // 方式三:
 @property (nonatomic, strong) NSString *__nonnull name;
{% endcodeblock %}
{% note warning %} 
#### 在`NS_ASSUME_NONNULL_BEGIN`和`NS_ASSUME_NONNULL_END`之间,定义的所有对象属性和方法默认都是nonnull
{% endnote %}
{% codeblock null_resettable作用: get不能返回为空, set可以为空 lang:objc %}
// 书写方式:
@property (nonatomic, strong, null_resettable) NSString *name;
{% endcodeblock %}
{% note warning %} 
#### 如果使用null_resettable,必须重写get方法或者set方法,处理传递的值为空的情况
{% endnote %}
{% codeblock _Null_unspecified:不确定是否为空 lang:objc %}
// 书写方式只有这种
// 方式一
@property (nonatomic, strong) NSString *_Null_unspecified name;
// 方式二
@property (nonatomic, strong) NSString *__null_unspecified name;
{% endcodeblock %}
{% codeblock 以下这种写法结果是可以为空 lang:objc %}
NS_ASSUME_NONNULL_BEGIN

@property (nonatomic, strong, nullable) NSString *name;

NS_ASSUME_NONNULL_END
{% endcodeblock %}
***
{% note info %} 
 #### 相关链接：无
 []()
{% endnote %}
{% note warning %} 
 转载请注明出处 
 文章有问题请指出
{% endnote %}