---
title: AboutJava
date: 2017-09-06 15:29:41
categories: Java
keywords: 简单题目
tags: 
---

1、判断一个数（小于10位）的位数。
输入999，则输出 “它是个3位的数！
```
    
public class HelloWorld{
    public static void main(String[] args){
        int num = 999;
        int count = 0;
        if(num>=0&&num<=999999999){
            while(num>=1){
                count++;
                num/=10;
       }
            System.out.println("它是个"+count+"位的数！");
        }
        else{
            System.out.println("输入有误");
        }
    }
}

```

    