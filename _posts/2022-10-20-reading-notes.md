---
layout: post
title: "Reading Notes"
author: "Fuku"
tags: Reading
---

> A great challenge of life: Knowing enough to think you are right, but not knowing enough to know you are wrong.
>
> --- Neil

> Tôi muốn mọi người biết rằng có nhiều đứa trẻ vẫn đang chống chọi từng ngày để lớn lên thành người tử tế.
>
> -- Tìm mình trong thế giới hậu tuổi thơ - Đặng Hoàng Giang

> Chúng ta dễ vướng vào cảm giác ganh tỵ vì nguyên do đơn giản là chúng ta quen thuộc với cuộc đời của mình hơn cuộc đời của người khác.
>
> -- BÀN VỀ HAM MUỐN - William B. Irvine

> chúng ta phần lớn không biết đến những nỗ lực, nhu cầu và hành động tử tế của những người xung quanh. Do đó, khi điều tốt đẹp đến với họ, ta không hề nhận ra họ xứng đáng với những điều đó, hay ở mức độ nào đó, họ xứng đáng với chúng nhiều như chúng ta.
>
> -- BÀN VỀ HAM MUỐN - William B. Irvine

> Thông minh là năng lực thích nghi với thay đổi.
>
> -- Stephen Hawking

>  Thay vì chỉ chăm chăm theo đuổi 1 góc nhìn, chúng ta nên phát triển nhiều góc nhìn khác nhau để suy nghĩ về thế giới. Càng có nhiều góc nhìn, bạn càng có thêm công cụ để tư duy.
>
> -- Unknown Author

> Tình yêu là từ dùng để chỉ những ham muốn tình dục của người trẻ, thói quen của người trung niên và sự phụ thuộc lẫn nhau của người già
>
> -- John Ciardi

> Những người đã chuẩn bị cho khổ đau là những người kiên cường nhất trước khổ đau. Những người trông chờ sự khảo nghiệm là những người sẵn sàng nhất để đối mặt với khảo nghiệm. Kiên định đâu phải là lúc nào cũng cảm thấy phấn chấn, mà nghĩa là đôi khi bạn bằng lòng với cảm giác không mấy tốt đẹp.
>
> -- markmanson.net

> Niềm vui của việc cho một cách tự nguyện và không giới hạn chuyển thành nỗi lo sợ về việc có thể không được nhận. Người ấy – chồng bạn, người yêu bạn, con bạn – tự nhiên trở thành quá quan trọng với bạn. Bạn lo lắng về những gì có thể xảy ra. Những gì họ sắp làm. Và ở thời điểm đó, tình yêu dừng lại.


**Q**: Theo các bác thì tại sao các ứng dụng như Discord, Slack, Microsoft Teams, Skype, Postman lại chọn Electron framework của js - phổ biến nhưng rất nặng và chậm. Hay 1 số app như Twitter là 1 hybrid, cũng sử dụng js cũng nặng và chậm nhưng chúng vẫn thành công và phổ  biến vậy ạ? Liệu các app đó ban đầu chọn những framework hiệu suất hơn hay native liệu sự thành công của chúng có giảm đi ko?

**A**: Sếp mình bảo ban đầu người ta quan  tâm đến business có kiếm được tiền k. Kiếm được rồi thì đập đi xây lại còn được


**Q**: Hi các anh ạ, cho em hỏi với câu hỏi này thì solution tối ưu nhất là như thế nào ạ:
"Giả sử có một tính năng mới yêu cầu thay đổi tên cột trong cơ sở dữ liệu SQL của bạn, bạn sẽ làm thế nào để thực hiện điều đó mà không bị ngừng hoạt động?"

**A**: tạo col mới, chỉnh code double write data vào, backfill data cũ qua, tạo index mới, switch code qua read col mới, backup data, drop col cũ.
Câu hỏi này thường lọc đc các ứng viên ko có kinh nghiệm làm với production mà có requirements ít downtime, cần live db migration / rollback. Trả lời là "em nhảy vào chạy command" là tạo ra table lock, dừng transaction thì fail ngay.

**Q**: Cho em hỏi về cấu trúc hiện tại của project em có ổn k.
Bình thường em thấy các project golang hay làm theo kiểu hàm tạo mới đối tượng rồi kèm theo method của đối tượng đó và truyền connect hay gì gì đó trong context, còn structure hiện tại của em nó cứ như js ý, viết tất cả thành funcion rồi truyền params vào. cho em hỏi các hiện tại em có ổn không, và nếu không thì sự khác biệt là gì.

**A**: Giải thích ngắn gọn là cách của e là "hướng thủ tục" (procedure) còn cái e hay thấy là "encapsulation" (bao đóng - moá dịch ra chuối vãi), do Go ko có OOP nên mình ko dùng "hướng đối tượng". Tuy nhiên encapsulation giúp em xây dựng abstraction, quản lý code dễ hơn (do scope của method và global function khác nhau). Còn lại e tìm hiểu tiếp nha.

> Tuyển ERP dev nói chung Odoo nói riêng mà tìm người giỏi có nhiều điểm khó và khác với dev thuần. Bởi vì các framework ERP cần 1 thời gian phát triển rất lâu và focus vào các bài toán phức tạp về business nên công nghệ thường cũ, code theo kiểu riêng, ko chạy theo các skills trending, khó làm đẹp cv nên dev fresher ít người theo. Dev ERP thường là làm customization, dựa trên base sẵn nên nếu nắm dc cơ bản thì sau đó rất dễ "làm được" mọi thứ, nhưng để "làm đúng", "làm tốt" thì cần có sự am hiểu business và technical architect, thường là người đã senior 1 công nghệ khác chuyển sang làm. Senior ERP/Odoo hầu như đều có 1 nửa kỹ năng BA và Consultant, thường định hướng lập team riêng nhận dự án triển khai hoặc outsource. Mà đối tượng này thì hoặc chấp nhận mức lương vừa phải nhưng công việc nhàn để có thời gian làm riêng, hoặc kiêm nhiệm nhiều vai trò khác trong các công ty lớn. Fen vào group Odoo trên fb sẽ thấy, thảo luận về tech toàn mấy ông già làm CTO, CEO, Tech Lead, hoặc amateur trái ngành nhảy sang thôi.


**Q**: Môi trường bank học hỏi được gì ko ạ, em  vẫn thích kiểu công ty có sản phẩm gì đó bán rồi mình vô code

**A**: học được nghiệp vụ tốt, chuyển bank khác là lợi thế; học các deal với chính trị, quy trình dày đặc; đi làm có giờ có giấc ăn mặc chỉnh chu tác phong đàng hoàng học được tính kỷ luật. còn về tech thì cũng bình thường. nhiều cái cũng ối dồi ôi lắm

**A**: survival trong 1 công ty toàn chính trị là 1 bản lĩnh

**Q**: ...nhiều cty build phần mềm từ đầu tốn nhiều chi phí cho lập trình mà độ ổn định lại kém hơn opensource có sẵn. Tại sao họ ko lấy chi phí đó tập trung vào marketing để nó tới được với những end user ko quan trọng sâu đến công nghệ nào đã tạo ra nó ?

**A1**: Khi return on investment nó tốt thì làm. build or buy bài toán khá đơn giản: 2 cái là solutions cho cùng 1 vấn đề nào đó: feature / fix bug. Cái feature / bug đó đáng giá X dollars.
Development cost để build from scratch/fork cái opensource thì là:
(salary per hour * engineering hours) = Y dollars

Cái Y này tối thiểu là nó cần thấp hơn X.
Sau đó nó sẽ có X-Y1, X-Y2, X-Y3 vì cùng 1 quỹ thời gian, bạn có thể chọn làm các feature khác nhau hoặc fix các bug khác nhau.
Cần rank tất cả dựa trên cost/return để biết đc cái nào có thể có highest impact thì làm trước.
vd: Để chạy ecommerce system nhanh hơn thì có thể tằng page size của kernel từ 4bytes lên 128bytes. Chạy nhanh hơn thì đỡ cost infra hơn -> giảm infra cost đc 10k 1 tháng

Cost để fork linux kernel để tăng page size:
- Inigital developement: 5 engineers * (8h * 5d) = 200 eng hours
- Long term maintenance: 8h * 5d * 1 engineer = 40 eng hours / month

Vậy cost cho 1 năm là 680 eng hours. 
Nếu trả engineer hơn đc 10_000 / 680 = 14.7 USD / h (3k / tháng) thì ko đáng 🙂
good luck kiếm đc C engineer để fork kernel dưới 3k 1 tháng :))

**Q**: Đi phỏng vấn nhận được câu xử lý 1tr rq/s thì trả lời sao cho hay các bác nhỉ.

**A1**: Đầu tiên hỏi a có thể làm rõ đề bài
Nếu k e sẽ có list câu hỏi để làm rõ 😅😁
List câu hỏi càng mạnh và 
Clear thì đc đánh giá càng cao, sát thực tế
Từ networl Lb, smart traffic, cache, db, backend, all

**A2**: Cache có vài loại sài loại nào cho business nào , cache ở layer nào , tương tự lb cũng có lb giữa svc với svc , lb giữa user với server , lb dns blablo =))) cứ có tiền thì được hết

**A**: > 1tr request 

Nên bắt đầu hỏi lại cho rõ ý đề bài:
- Network bandwidth ntn (1G, 10G?)
- 1 request nặng bao nhiêu (4kb, 18kb, 10MB, etc...)

Từ đó sẽ suy ra đc là mỗi máy nhận đc tối đa bao nhiêu request dựa trên network. Nếu nhiều máy thì cũng suy ra đc là cần bao nhiêu Load Balancer.

Sau đó tuỳ đề có thể đi vào data structure/schema design để giảm payload size, hay là compute requirement cho mỗi request (CPU/RAM) để triển khai thêm.

1000 requests thì read/write ratio vào DB ntn, scale DB ra sao cũng là 1 hướng khác.

**Q**: Tôi có 1m rps trừ hàng trong inventory, realtime cao, ACID TUYỆT ĐỐI, user không được mua hàng khi kho hết
Hãy thiết kế hệ thống chạy trơn tru, không lỗi,  triển khai optimal riêng theo solution của bạn. Mỗi phần thiết kế hãy trích cơ sở lý thuyết của solution đó :)))

**A**: Doạ đc junior thôi, chứ pv senior trở lên thì đều là 2 bên pv nhau: cty có thể đánh rớt ứng viên và ứng viên có thể đánh rớt cty. Cty hỏi tào lao thì lương phải đáng kể mới làm. Cty hỏi nghiêm túc, thực tế thì hấp dẫn ứng viên hơn

> Professionals speak truth to power. Professionals have the courage to say no to their managers.
>
> -- Clean Code by Robert C. Martin

> Nên chọn chỗ nào nhiều tiền
> Vì đằng đéo nào sau này em cũng không thích cả 2
> Xưa bị sếp vặt quá, hoá ra sếp đã đc tự do tài chính, ngồi thở không cũng có tiền
> Nên mấy sếp nói hay lắm
> Thì đéo phá là vẫn có đạo đức nghề nghiệp rồi
> Cái nào hiệu quả đơn giản dễ thì làm. Có hoa hồng cao thì càng nên làm, miễn đáp ứng đc các yêu cầu kĩ thuật
> nên là, thôi, bớt chửi lũ fake engineer lại, chúng nó giàu hơn mình
> ở cái xứ làm engineer nghèo như chó này, thì thằng thẳng lưng là dị tật, thôi gù tí mà no đủ cho cả nhà =))

