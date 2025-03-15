---
share: "true"
title: 【C语言】代码抽象技巧
---


## 让你变得更加不可替代 (~~更抽象~~)


### 1. 全加器代替加法
```c
int add(int a, int b){
	if(!a) return b;
	return add((a & b) << 1, a ^ b);
}
```

### 2. 使用更多的趋近符号
```c
int i = 100;
do{
	//something
}while(i --> 0);
```

### 3. 变更数组运算(一维)
```c
int a[5] = {1, 2, 3, 4, 5};
for(int i = 0;i < 5;i++){
	printf("%d\n", i[a]);
	printf("%d\n", (i - 1)[a + 1]);
}
```

### 4. 奇偶判断
```c
int num = 11;
printf("%d\n", num % 2 == 0);
printf("%d\n", num & 1);
```

### 5. 使用16进制数值 (-1的表示)
```c
0xffffffff
```

### 6. x * N
```c
x <<= 1; //x *= 2
x >>= 1; //x /= 2
x = (x << 1) + (x << 3); //x *= 10
```

### 7. 交换变量 (a ≠ b)
```c
int a = 2,b = 3;
a ^= b;
b ^= a;
a ^= b;

//or

a^=b^=a^=b
```

### 8. 不等于 [该方法可能会出现问题]
`a ≠ b <=> a ^ b`

### 9. int 转 char
```c
int a, b;
char ch;
ch = a ^ 48;
b  = ch ^ 48;
```