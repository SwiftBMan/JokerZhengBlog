---
title: Numbers_Data_And_BasicValues
date: 2018-05-11 11:46:00
updated:
categories:
    - iOS
tags:
    - Foundation/Fundamentals
---
---
<Excerpt in index | 首页摘要>  
    {% note default %}
    ### 文章摘要：Numbers, Data, and Basic Values
    {% endnote %}
 <!-- more -->
<The rest of contents | 余下全文>
***
<!-- 内容 -->
### Numbers
{% codeblock NSInteger、NSUInteger、NSIntegerMax、NSIntegerMin、NSUIntegerMax lang:objc %}
// 描述一个长整型数
typedef long NSInteger;
// 描述一个无符号长整型
typedef unsigned long NSUInteger;

// 我们可以这么写
typedef long MYInteger;
typedef NSInteger MYInteger;

// NSInteger最大值
NSIntegerMax
// NSInteger最小值
NSIntegerMin
// NSUInteger最大值
NSUIntegerMax

// 实质
#if __LP64__ || (TARGET_OS_EMBEDDED && !TARGET_OS_IPHONE) || TARGET_OS_WIN32 || NS_BUILD_32_LIKE_64
typedef long NSInteger;
typedef unsigned long NSUInteger;
#else
typedef int NSInteger;
typedef unsigned int NSUInteger;
#endif

#define NSIntegerMax    LONG_MAX
#define NSIntegerMin    LONG_MIN
#define NSUIntegerMax   ULONG_MAX

-----

#define LONG_MAX  __LONG_MAX__
#define LONG_MIN  (-__LONG_MAX__ -1L)
#define ULONG_MAX (__LONG_MAX__ *2UL+1UL)

{% endcodeblock %}
> 在构建32位应用程序时，NSInteger、NSUInteger是一个32位整数。64位应用程序将NSInteger、NSUInteger视为64位整数。

NSDecimal(一个表示base-10数字的结构。)
```objc
// 创建一个Decimal从另一个Decimail
void NSDecimalCopy(NSDecimal *destination, const NSDecimal *source);

// 把Decimals转成字符串
NSString * NSDecimalString(const NSDecimal *dcm, id locale);

// 压缩十进制结构
void NSDecimalCompact(NSDecimal *number);

// decimal相加。
NSCalculationError NSDecimalAdd(NSDecimal *result, const NSDecimal *leftOperand, const NSDecimal *rightOperand, NSRoundingMode roundingMode);

// decimal相减
NSCalculationError NSDecimalSubtract(NSDecimal *result, const NSDecimal *leftOperand, const NSDecimal *rightOperand, NSRoundingMode roundingMode);

// 相除
NSCalculationError NSDecimalDivide(NSDecimal *result, const NSDecimal *leftOperand, const NSDecimal *rightOperand, NSRoundingMode roundingMode);

// 相乘
NSCalculationError NSDecimalMultiply(NSDecimal *result, const NSDecimal *leftOperand, const NSDecimal *rightOperand, NSRoundingMode roundingMode);

// 10 * 10^power
NSCalculationError NSDecimalMultiplyByPowerOf10(NSDecimal *result, const NSDecimal *number, short power, NSRoundingMode roundingMode);

void NSDecimalRound(NSDecimal *result, const NSDecimal *number, NSInteger scale, NSRoundingMode roundingMode);

NSCalculationError NSDecimalPower(NSDecimal *result, const NSDecimal *number, NSUInteger power, NSRoundingMode roundingMode);

NSCalculationError NSDecimalNormalize(NSDecimal *number1, NSDecimal *number2, NSRoundingMode roundingMode);

typedef enum NSRoundingMode : NSUInteger {
    NSRoundPlain,
    NSRoundDown,
    NSRoundUp,
    NSRoundBankers
} NSRoundingMode;

NSComparisonResult NSDecimalCompare(const NSDecimal *leftOperand, const NSDecimal *rightOperand);

```



***
{% note info %} 
 #### 相关链接：
 []()
{% endnote %}
{% note warning %} 
 转载请注明出处 
 文章有问题请指出
{% endnote %}