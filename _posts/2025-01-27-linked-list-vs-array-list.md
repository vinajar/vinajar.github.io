---
title: "LinkedList vs ArrayList"
date: 2025-02-27T00:00:00+00:00
author: trannguyenhan
layout: post
permalink: /Linked-list-vs-array-list/
categories: Java Core
tags: [java, string, linked list, array list]
---

## ArrayList

- Triển khai: `ArrayList` được triển khai bằng mảng động (dynamic array)
- Tốc độ truy cập: truy cập phần tử bằng chỉ số (index) trong `ArrayList` nhanh hơn `LinkedList`
- Thay đổi kích thước: `ArrayList` hiệu quả khi thêm hoặc xóa phần tử ở cuối danh sách

## LinkedList

- Triển khai: `LinkedList` được triển khai dưới dạng danh sách liên kết (linked list). Mỗi phần tử trong danh sách liên kết trỏ đến phần tử tiếp theo
- Tôc độ truy cập: Do phải đi qua từng liên kết tuần tự một nên tốc độ truy cập các phần tử chậm hơn so vớ `ArrayList`