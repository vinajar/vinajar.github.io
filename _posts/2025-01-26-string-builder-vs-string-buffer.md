---
title: "Sự khác nhau giữa String Builder và String Buffer"
date: 2025-02-26T00:00:00+00:00
author: trannguyenhan
layout: post
permalink: /string-builder-vs-string-buffer/
categories: Java Core
tags: [java, string, string builder, string buffer]
---

## String buffer

`StringBuffer` là đồng bộ (synchronized), tức là luồng an toàn. Điều này có nghĩa là không thể có 2 luồng cùng truy cập phương thức của lớp `StringBuffer` đồng thời.

Do là luồng an toàn, đồng bộ vì vậy `StringBuffer` không hiệu bằng `StringBuilder`.

## String builder

`StringBuilder` là không đồng bộ (non-synchronized) tức là luồng không an toàn. Điều này có nghĩa là có thể có 2 luồng cùng truy cập phương thức của lớp `StringBuilder` đồng thời.

Do `StringBuilder` không đồng bộ, vì vậy `StringBuilder` hoạt động hiệu quả hơn `StringBuffer`.