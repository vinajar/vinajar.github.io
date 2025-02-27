---
title: "== và equals trong so sánh chuỗi khác nhau như thế nào?"
date: 2025-01-18T00:00:00+00:00
author: trannguyenhan
layout: post
permalink: /equals-vs-==-in-string/
categories: Java Core
tags: [java, equals]
---

## So sánh `equals` và `==` trong chuỗi

Trong Java, `equals` và `==` đều dùng để so sánh đối tượng, tuy nhiên cách sử dụng của chúng có sự khác biệt. Sự khác biêt rõ ràng nhất được thể hiện qua việc so sánh giữa 2 chuỗi.

Ví dụ có 2 chuỗi khai báo như sau: 

```java
String s1 = "vinajar";
String s2 =  new String("vinajar");
```

Nếu in:

```java
System.out.println(s1 == s2);
System.out.println(s1.equals(s2));
```

Kết quả trả ra được sẽ là: 

```bash
false
true
```

Bởi vì, khi dùng `equals` là đang so sánh nội dung của 2 chuỗi đó, chúng đều là `vinajar` và vì thế chúng bằng nhau. Còn khi dùng so sánh `==` là đang so sánh về vị trí bộ nhớ lưu trữ được tham chiếu trên bộ nhớ `heap` của từng biến. Chúng phải có cùng địa chỉ thì so sánh `==` mới trả ra giá trị `true`. `s2` được khởi tạo `String s2 =  new String("vinajar");` vì thế chúng đang có một vùng nhớ mới trên heap.

Vậy còn khi khởi tạo như dưới thì kết quả so sánh là gì: 

```java
String s1 = "vinajar";
String s2 = "vinajar";

System.out.println(s1 == s2);
System.out.println(s1.equals(s2));
```

Kết quả nhận được sẽ là: 

```bash
true
true
```

Khi khởi tạo một chuỗi mới `s2 = "vinajar"` (**String literals**) không sử dụng từ khóa `new`, hệ thống sẽ tìm trong **Spring Pool** xem chuỗi khởi tạo có nội dung đã chuỗi giống với một chuỗi nào đó đã được khởi tạo trước đó không, nếu có thì sẽ được trỏ vào cùng vị trí bộ nhớ. Còn khi dùng từ khóa `new` luôn luôn được phân bổ bộ nhớ mới trên heap. Vì thế khi khởi tạo `String` nên khởi tạo bằng String literals để tiết kiệm bộ nhớ.

## Sử dụng `equals` và `==`

Vậy `==` và `equals` được dùng khi nào:

- Sử dụng `==` cho các kiểu dữ liệu nguyên thủy
- Việc so sánh đối tượng mà so sánh cả địa chỉ là rất hiếm, vì vậy trừ các tác vụ đặc biệt thì so sánh đối tượng hay so sánh chuỗi luôn dùng `equals`