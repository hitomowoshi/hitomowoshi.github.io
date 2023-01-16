---
layout: post
title:  "Random thoughts (collected from someone somewhere)"
author: "Fuku"
comments: true
tags: Random
excerpt_separator: <!--more-->
sticky: true
hidden: true
---

# Design patterns in Golang

> I don’t concern myself with design patterns in Golang, mainly because most of them in my opinion complicate things unnecessarily.

> I know that obsessing about design patterns can make the code harder to read, and that it is not an exact science. But we should embrace and welcome them, not fear them.

# Golang and security

> Go ecosystem is nice for networking stuff, so probably we gonna have more and more "hacking" stuff written in go

# Frameworks

> What I found works best for me is to read through one or two frameworks to learn their implementation architecture and then build a very minimalistic version that works best for me!

# DÀNH CẢ THANH XUÂN CHO NHỮNG ĐIỀU VỤN VẶT NƠI CÔNG SỞ

This topic make me think that I should do something to prevent this

- check tin nhắn telegram &rarr; ok t sẽ disable noti trên telegram
- hỏi lại người hỏi mình vì méo hiểu câu hỏi của người ta nghĩa là gì dm =__= &rarr; cái này thì chịu, à có cách là out khỏi dự án, tìm kiếm đồng đội tốt hơn, m nghỉ m đủ tốt để có được đồng đội tốt hơn chưa ???
- chỉnh template báo cáo, thêm field, sửa view dcm &rarr; nghỉ việc đi
- chạy ngược từ tầng 1 lên tầng 5 vì quên đồ 
- đăng nhập vào hrm để xem giờ checkin &rarr; xem giờ trên máy quét ngay lúc checkin xong

# Mechanical Sympathy

Ngày trước, trong lúc mood mình đang khá tệ thì sếp Andrew có lôi mình đi ăn. Lúc đó sếp có nói một ý, đại loại là sứ mệnh của công ty, cụ thể ơn là công việc mình đang làm là mang lại value cho doanh nghiệp. Nếu như mang lại giá trị cho khách hàng/doanh nghiệp không phải là mục tiêu của mình, vậy thì có lẽ mình sẽ không đi được lâu theo con đường này.

Sau bữa đó cứ băn khoăn tự hỏi mãi, rốt cuộc mình có đang làm việc vì mang lại lợi ích, giá trị cho khách hàng, cho doanh nghiệp của mình không. Nói có thì không đúng, nhưng nếu như là không, vậy thì mục tiêu mình hướng đến là gì? Và nếu như nó khác với định hướng chiến lược của công ty thì mình phải chuẩn bị cho một ngày không xa mình rời khỏi tổ chức này, vậy mình đã chuẩn bị được gì cho cái viễn cảnh đó chưa.

Làm khách hàng hài lòng chắc chắn không phải là thứ mình hướng đến tuy nhiên công việc hiện tại mình lại phải làm việc với khách hàng rất nhiều. Đương nhiên làm việc thì giao tiếp là cần thiết, nhưng mình cần một môi trường mà sự giao tiếp dùng để hợp tác, giúp đỡ nhau tìm ra giải pháp, người giỏi giúp đỡ người mới, nếu ai cũng không biết làm thì cùng nhau tìm kiếm giải pháp bên ngoài, gather thêm những người có năng lực để cùng nhau khắc phục vấn đề hơn là những câu chuyện xoi xét, blame đồng đội, nhờ vả, đùn đẩy công việc và dùng những cách nói chuyện như ??? IN HOA TOÀN BỘ MESSAGE inbox kín để complain. Nó không giải quyết được việc gì ngoài việc lan tỏa sự toxic ra xung quanh. Mình rất mệt mỏi với những sự toxic kiểu như vậy.

Thôi dừng =))) càm ràm đủ rồi giờ thì vào vấn đề chính, cái idea này khá là hay. Và mình thấy nó là một solution phù hợp với mình. Mình quá mệt mỏi khi phải giao tiếp với con người, luôn luôn sợ làm người khác tự ái, luôn sợ làm phiền người khác, luôn sợ sự đen tối và toxic của mình làm ảnh hưởng đến năng lượng của người khác, luôn mệt mỏi vì cảm thấy hối hận vì lỡ vụng miệng nói gì đó không hợp tình huống nhưng lại chẳng dám xin lỗi vì cứ băn khoăn không biết người ta có để ý hay không. Vậy thì để đỡ mệt mỏi thì thôi, đừng cứ để đầu óc xoay lòng vòng quanh những người khác, kệ cmn khách hàng đi, mày viết code cho ai? Đương nhiên là cho máy tính chạy, vậy thì hãy nghĩ cho máy, cho chiếc server đang chạy những dòng code của mày, viết sao cho nó *sống* một cách có ích, sao cho nó làm việc một cách logic đúng như sự logic vốn có của nó, 0 là 0 mà 1 là 1. Viết sao cho nó đừng bị quá tải, đừng làm nó mệt, dùng bất kỳ framework nào cũng hay tôn trọng nó, hiểu nó trước khi muốn nó biến thành hình hài nào mới, trước khi định vặt tay bẻ chân tính năng của nó. Lập trình nhiều khi có những logic rất phức tạp nhưng chắc chắn là nó sẽ không khó chịu như việc mày phải deal với ty tỷ kiểu người khác nhau trên thế giới này.

**Mechanical Sympathy** - Khi hệ thống chậm bạn nghĩ đến điều gì? Hãy nghĩ đến làm sao cho code của mình thân thiện, đồng điệu và họat động tốt hơn với phần cứng trước khi nghĩ đến scaling. (lập trình phần mềm đồng điệu với phần cứng - hardware and software working together in harmony)