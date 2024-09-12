<div align="center"><img src="cover2.png" width="800"></div>

<head>
  <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
  <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
      tex2jax: {
      skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
      inlineMath: [['$','$']]
      }
    });
  </script>
</head>

# Computer Science

## Types of declare

 <div align="center"><img src="./M1Pic/C1.png" width="400"></div>

 ## Syntaxs

 ### printf

> %d：输出整数。%f：输出浮点数。%c：输出字符。%s：输出字符串。

    #include <stdio.h>
    int main() {
        int age = 25;
        float height = 175.5;
        char grade = 'A';
        char name[] = "Alice";
        
        printf("Name: %s\n", name);       // 输出字符串
        printf("Age: %d\n", age);         // 输出整数
        printf("Height: %.1f\n", height); // 输出浮点数，保留1位小数
        printf("Grade: %c\n", grade);     // 输出字符
        
        return 0;
    }
    Name: Alice
    Age: 25
    Height: 175.5
    Grade: A

### scanf

    scanf("格式字符串", &变量1, &变量2, ...);
> 格式字符串：定义要读取的数据类型。
变量：存储用户输入的值，需要传入变量的地址（用 & 取地址符号）。

    #include <stdio.h>

    int main() {
        int age;
        float height;
        char grade;
        char name[50];  // 预留50个字符空间存储输入的字符串
        
        printf("Enter your name: ");
        scanf("%s", name);  // 输入字符串
        
        printf("Enter your age: ");
        scanf("%d", &age);  // 输入整数时要使用 & 符号
        
        printf("Enter your height (in cm): ");
        scanf("%f", &height);  // 输入浮点数
        
        printf("Enter your grade: ");
        scanf(" %c", &grade);  // 输入字符时也要使用 & 符号，前面有空格防止读取换行符
        
        // 输出刚才输入的值
        printf("\nName: %s\n", name);
        printf("Age: %d\n", age);
        printf("Height: %.1f cm\n", height);
        printf("Grade: %c\n", grade);
        
        return 0;
    }
