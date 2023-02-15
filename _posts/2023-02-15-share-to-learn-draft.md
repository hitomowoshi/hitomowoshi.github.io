---
layout: post
title:  "Share To Learn Draft"
author: "Fuku"
tags: Random
---

Some Share To Learn Idea but just draft & brief content

# Mechanical Sympathy

ref:

[Tìm hiểu về khái niệm Mechanical Sympathy trong phần mềm.](https://batnamv.medium.com/t%C3%ACm-hi%E1%BB%83u-v%E1%BB%81-kh%C3%A1i-ni%E1%BB%87m-mechanical-sympathy-v%C3%A0-b%E1%BB%99-th%C6%B0-vi%E1%BB%87n-lmax-disruptor-4d553dc7fa55)

[Concurrency is hard](https://mkralka.github.io/blog/concurrency-is-hard)

## the idea/definition
Man and machine working togenther in harmony
Sorfware and hardware working together in harmony
Ki Ken Tai Ichi harmonize the internal energy (ki), the sword (ken) and the body (tai) to maximize the power of your strike

Apply a Scentific Mindset:
- Draw on Experience
- Do your Reasearch
- Learn by Experimenting

Understanding the safety features will greatly improve your understanding of the model:
- **Bounds checking** is any method of detecting whether a variable is within some bounds before it is used.
- **forward error correction** is a method of obtaining error control in data transmission in which the source (transmitter) sends redundant data and the destination (receiver) recognizes only the portion of the data that contains no apparent errors
- **RAID (redundant array of independent disks)** is a data storage virtualization technology that combines multiple physical disk drive components into one or more logical units for the purposes of data redundancy, performance improvement, or both.
- Circuit Breaker (pattern)
- replication
- congestion control
- error/exception handling
- automatic memory management

Apply telemetry and perform real-time monitoring on the data
Requires efficient collection, centralised aggregation, analysis, and alerting

## Mechanical Sympathy in Action:

- It is all about experience and understanding executed with finesse
- Know where the limits are and plan to stay inside them
- React appropriately to spikes in load...
- ...apply batching to amortise costs and back-off strategiesto prevent failure
- Do you know the fundamentals of how your platform works?
- Networks are faster than Storage
- Memory Access Patterns Matter

## Why

- Chia sẻ bộ nhớ (share memory) giữa các thread rất dễ gặp lỗi, chúng ta phải rất cẩn thận khi sử dụng.
- Sử dụng bộ nhớ của CPU (CPU cache) nhanh hơn sử dụng bộ nhớ đệm chính (DRAM), nhưng nếu sử dụng mà không hiểu rõ cách hoạt động (ví dụ như khái niệm cache lines v.V...) sẽ làm mọi thứ trở nên tồi tệ hơn.

## Shared memory

Các process/thread của CPU sẽ sử dụng chung một vùng không gian nhớ chung (share memory). Việc tương tác giữa hai process sẽ hoàn toàn do việc đọc/ghi trên vùng nhớ chung này. OS không hề can thiệp vào quá trình này, thế nên shared memory là phương pháp nhanh nhất (nhanh về mặt tốc độ) để các process nói chuyện với nhau. Tuy nhiên, nhược điểm của phương pháp này là các process phải tự quản lý việc đọc ghi dữ liệu, và quản lý việc tranh chấp tài nguyên (race condition).

**Race condition**

**CPU caches**
L1, L2, L3, Main memory (DRAM)

**cache lines**

## Concurrent programming

### Tương tranh - Mutual Exclusion (cơ chế loại trừ lẫn nhau)

Trong ngành khoa học máy tính, tương tranh là một tính chất của các hệ thống bao gồm các tính toán được thực thi trùng nhau về mặt thời gian, trong đó các tính toán chạy đồng thời có thể chia sẻ các tài nguyên dùng chung. Hoặc theo lời của Edsger Dijkstra: “Tương tranh xảy ra khi nhiều hơn một luồng thực thi có thể chạy đồng thời.” Việc cùng sử dụng các tài nguyên dùng chung, chẳng hạn bộ nhớ hay file dữ liệu trên đĩa cứng, là nguồn gốc của nhiều khó khăn. Các tranh đoạt điều khiển (race condition) liên quan đến các tài nguyên dùng chung có thể dẫn đến ứng xử không đoán trước được của hệ thống. Việc sử dụng cơ chế loại trừ lẫn nhau(mutual exclusion) có thể ngăn chặn các tình huống chạy đua, nhưng có thể dẫn đến các vấn đề như tình trạng bế tắc (deadlock) và đói tài nguyên (resource starvation).

Tóm lại Mutual Exclusion là ta phải đảm bảo trong một thời điểm chỉ duy nhất 1 thread được thực thi vào share memeory. -> locking/CAS(compare and swap)

### Visibility of Change

"Những thay đổi được thực hiện bởi một luồng (thread) với dữ liệu chia sẻ (share data), sẽ được thông báo và hiển thị (visible) ngay lập tức với các thread khác để duy trì tính nhất quán của dữ liệu (data consistency)"

**sharing memory by communicating**

## LMAX Disruptor

### Ring Buffer


[Arcturus — Inventory Processing System](https://engineering.tiki.vn/arcturus-inventory-processing-system/) an application of LMAX Disruptor

# The silent majority

# Tăng tốc data base