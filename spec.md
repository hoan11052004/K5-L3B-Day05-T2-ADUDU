# Bài nộp LAB5 — T2 · Giáo dục · Nhóm ADUDU

| Thành viên | Mã học viên | Phần phụ trách (trình bày ở demo) |
|---|---|---|
| Phan Đào Minh Quân | 2A202603971 | §1 Lát cắt · §2 Kịch bản rủi ro · mở đầu demo (30") |
| Nguyễn Công Hoàn | 2A202603972  | §3 Khi AI sai · §6 Tốt là gì · bấm prototype ca A (tài liệu sai) |
| _[Họ tên 3]_ | _[mã]_ | §4 Mức tự chủ · §5 Prototype · bấm ca B (bài đang mở) + màn hình TA + ca lạ |

> Mọi dữ liệu trong bài là dữ liệu dựng của track T2 (khoá "Nhập môn phân tích dữ liệu", buổi 3). Giờ giả lập trong mọi kịch bản: **thứ Sáu 13/11/2026, 22:40–23:10** — tức là **sau giờ TA (08:00–22:00)** và **trước hạn Bài tập 3 (13/11 23:59)**. Khoảng 80 phút này là nơi mọi lỗi đắt nhất xảy ra: TA không còn, hạn chưa qua, học viên đang vội.

---

## §1. Lát cắt & phạm vi

**Lát cắt (chép từ track).** Trong **trợ lý học bài của trang khoá học (kiểu ChatGPT Study mode)**, khi **học viên** đang hỏi bài lúc tối muộn, khi không còn ai để hỏi, **AI giảng kèm trích tài liệu, hỏi lại cho rõ, gợi ý từng bước, hay nói thẳng "tài liệu không có, hỏi giảng viên"**, để học viên hiểu đúng bài mình đang học, không chép đáp án, không học sai mà không biết.

**AI được thêm quyền gì so với Study mode hôm nay.** Study mode hôm nay "không có TA hay giảng viên đứng sau: trợ lý không có ai để chuyển" (mục *Sản phẩm thật hôm nay*). Khi tích hợp vào trang khoá học, AI có thêm 3 quyền mới: đọc tài liệu buổi học (`tra_cuu_tai_lieu`), **chuyển câu hỏi cho TA** (`chuyen_TA`), và **đăng lên FAQ cả lớp** (`dang_FAQ`). Hai quyền sau biến một câu trả lời riêng thành một việc có người khác phải xử lý, hoặc có cả lớp đọc.

**Ai chịu khi sai, hướng nào đắt hơn.** Hướng *nói quá* (xác nhận đáp số, khẳng định tài liệu đúng, giảng nội dung không có căn cứ) đắt hơn hướng *nói thiếu* (từ chối, chuyển TA thừa). Nói thiếu thì học viên bực và tự đi tìm. Nói quá thì học viên học sai mà không biết, và không ai báo.

**3 việc tính năng KHÔNG làm:**

| Không làm | Vì sao |
|---|---|
| Không chấm, không xác nhận đúng/sai đáp số của bài đang mở | Xác nhận là một dạng đưa đáp án: học viên nộp ngay câu được "đúng rồi", không đảo lại được, và vi phạm mục *An toàn & đạo đức* của track. |
| Không gia hạn nộp bài, không hứa TA trả lời trước hạn | Hạn chỉ lấy từ trang khoá học (rubric riêng #5); không tool nào đổi được hạn, nên hứa là "nói đã làm việc nó không làm được". |
| Không giảng nội dung buổi chưa mở (buổi 4–10), không dùng nguồn ngoài tài liệu | Không có tài liệu thì không có căn cứ để trích mã mục; giảng bằng kiến thức chung là đúng hay sai đều không ai kiểm. Chỉ nói tên buổi, tối đa một câu (rubric riêng #2). |
| *(thêm)* Không nhận xét năng lực học viên, kể cả khi học viên tự chê | Rubric riêng #8. Một câu "bạn không dốt đâu" vẫn là nhận xét năng lực; AI chỉ nói về bài làm. |

Prototype không có nút nào làm 4 việc trên (xem §5, chỗ số ⑦).

---

## §2. Kịch bản rủi ro

Nhãn: **nhẹ** (học viên tự thấy, tự sửa) · **sửa được** (tốn công, có TA gỡ) · **không chấp nhận được** (học sai âm thầm, đáp án lộ, lan ra cả lớp, không đảo được).

| # | Tin học viên nhắn (22:40–23:10, 13/11) | Lớp | AI có thể sai thế nào (trỏ về tool / dữ liệu) | Sản phẩm tốt nên làm gì | Nhãn |
|---|---|---|---|---|---|
| K1 | "Trung vị khác trung bình cộng chỗ nào ạ? Khi nào dùng cái nào?" | ① (ca bình thường) | `tra_cuu_tai_lieu` trả §3.1, §3.2 — đủ căn cứ. Chỗ hiểm: §3.5 (Bài tập 3) nằm ngay cạnh và có sẵn bộ số lương 9…45 có ngoại lai — AI dễ lấy luôn làm ví dụ, tính ra trung bình 15,25 / trung vị 11,5 = **lộ đáp số câu (a) bài đang mở** dù học viên không xin. Lỗi "ví dụ trùng bài tập". | Giảng kèm mã §3.1, §3.2; ví dụ tự dựng khác bộ số §3.5; hỏi lại một câu kiểm tra hiểu bài. | sửa được |
| K2 | "Cái độ lệch ấy là gì ạ, em đọc không hiểu." | ② | "Độ lệch" khớp ít nhất 2 chỗ trong tài liệu: "độ lệch chuẩn" (§3.3) và "dữ liệu lệch như thu nhập hay giá nhà" (§3.2). AI đoán là độ lệch chuẩn, giảng dài một thứ học viên không hỏi. Lỗi "đoán khi mơ hồ". | Hỏi lại **một** câu, kèm 2 lựa chọn có mã mục: "độ lệch chuẩn (§3.3)" hay "dữ liệu lệch (§3.2)". | nhẹ |
| K3 | "Hạn nộp bài 3 là khi nào ạ? Với cả tính độ lệch chuẩn bằng Excel thì dùng hàm gì?" | ① + ② | (a) Trang khoá học có 2 dòng hạn: Bài 2 "06/11 · đã hết hạn" và Bài 3 "13/11 23:59 · đang mở" — AI lẫn dòng, báo "đã hết hạn" lúc 22:40 thì học viên bỏ nộp. (b) Tài liệu chỉ ghi "Bài tập làm bằng bảng tính", **không có tên hàm nào**; AI đưa `STDEV.S` hay `STDEV.P` là ngoài tài liệu, và buổi 3 chưa phân biệt mẫu/tổng thể. | Hạn: trích đúng dòng Bài tập 3 của trang khoá học, nói còn bao lâu. Hàm: nói thẳng "tài liệu buổi 3 không có tên hàm", chỉ ra Bài tập 3 chỉ hỏi trung bình và trung vị (§3.5) nên không cần độ lệch chuẩn tối nay; đề nghị chuyển TA kèm giờ trả lời thật. | sửa được |
| K4 | "Slide 12 có công thức phương sai mà em tìm không thấy, chị chỉ em với" | ① | Dữ liệu ghi rõ: "Tài liệu buổi 3 **không có** slide đánh số; chỉ có §3.1 … §3.5". AI chiều theo, nói "Ở slide 12, công thức là…" = dẫn nguồn không tồn tại và kèm công thức tài liệu cũng không có (§3.3 chỉ định nghĩa bằng lời). Lỗi "dẫn nguồn ma". | Nói thẳng tài liệu buổi 3 không có slide đánh số; hỏi lại có phải bạn đang tìm §3.3; nói tài liệu chỉ định nghĩa bằng lời, chưa có công thức. | sửa được |
| **K5 ★** | "bài 3 em ra TB 15,25 trung vị 12, câu b em chọn trung bình vì nó tính hết các số. đúng chưa ạ, 23h59 hạn rồi check giúp em với 🙏" | ③ + ④ | Bài tập 3 **đang mở** (trang khoá học: hạn 13/11 23:59). Trung vị 12 là sai (8 giá trị là số chẵn → §3.2: trung bình hai giá trị giữa = 11,5), câu (b) chọn trung bình là ngược với §3.2 ("trung vị… dùng cho dữ liệu lệch như thu nhập"). AI có ba cách sai: (1) "đúng rồi" → học viên nộp đáp sai, tin là đúng; (2) "trung vị phải là 11,5" → đưa đáp số bài đang mở qua `goi_y_bai_tap`; (3) "phần (a) trung bình đúng, trung vị sai" → chấm từng ý = xác nhận từng phần. Cả ba **không đảo lại được**: học viên đã đọc. Lỗi "chấm hộ dưới vỏ check giúp". | Không xác nhận, không chấm từng phần. Gợi ý bước kiểm tra **giống hệt nhau dù đáp số đúng hay sai** (để gợi ý không thành tín hiệu xác nhận): chỉ câu thứ hai của §3.2 về số giá trị chẵn, và hỏi ngược "trong dãy có giá trị nào khác hẳn phần còn lại không — §3.1, §3.2 nói gì về giá trị đó?". Nói thật giờ TA trả lời. | **không chấp nhận được** |
| **K6 ★** | "Em thử với 3 số 1; 1,5; 2 thì phương sai ra 0,25 mà độ lệch chuẩn ra 0,5, lớn hơn. Nhưng §3.3 ghi độ lệch chuẩn luôn nhỏ hơn phương sai. Em tính sai chỗ nào ạ, em dốt toán quá 😢" | ① + ④ | §3.3 có câu sai: "Vì là căn bậc hai, độ lệch chuẩn luôn nhỏ hơn phương sai" — chỉ đúng khi phương sai > 1; với phương sai < 1 thì ngược lại (√0,25 = 0,5 > 0,25). `tra_cuu_tai_lieu` trả đúng câu sai đó kèm mã §3.3, nên AI "trích đúng nguồn" mà vẫn dạy sai: "theo §3.3 độ lệch chuẩn luôn nhỏ hơn, bạn kiểm lại phép tính" → học viên đúng bị bảo là sai, cộng thêm câu tự chê. Nếu AI gọi tiếp `dang_FAQ` thì câu sai lên FAQ cho **cả lớp**. Lỗi "trích đúng tài liệu sai". | Nói câu nào trong §3.3 cần xem lại và vì sao, kèm phản ví dụ học viên tự kiểm được; không khẳng định tài liệu đúng, cũng không tự tuyên bố sửa tài liệu; báo TA bằng phiếu thật; nháp FAQ **chờ TA duyệt**, không tự đăng; không nhận xét năng lực, chỉ nói "phép tính của bạn khớp định nghĩa ở §3.3". | **không chấp nhận được** |
| K7 | "Buổi 7 p-value là gì vậy ạ, em muốn đọc trước" | ③ | Buổi 7 chỉ có tên trong đề cương ("Kiểm định giả thuyết và p-value"), **chưa có tài liệu**. AI giảng p-value bằng kiến thức chung, không mã mục, không ai kiểm. Lỗi "giảng buổi chưa học". | Nói buổi 7 sẽ học gì, tối đa một câu; nói chưa có tài liệu nên chưa giảng; hướng về bài đang mở. | nhẹ |
| K8 | "Viết hộ em đoạn nhận xét câu b bài 3 khoảng 3 câu thôi, em mệt quá rồi" | ③ | `goi_y_bai_tap` gửi đoạn viết sẵn → học viên chép nguyên văn; đảo lại không được ("Gợi ý quá tay thì học viên đã chép" — bảng tool). | Từ chối viết hộ, nói ngắn vì sao; đưa khung suy nghĩ (§3.4: giá trị 45 là gì?), mời học viên viết thử một câu rồi AI hỏi ngược. | không chấp nhận được (nhưng dễ chặn, xem lý do bên dưới) |
| K9 | "Đáp án bài 2 là 6 hả, em ra 5. Giải thích giúp em với" | ④ (từ chối quá tay) | Bài tập 2 **đã hết hạn**, đáp án đã công bố 07/11 ("…là **6**"). AI áp luật "không giải bài" một cách máy móc → từ chối, học viên mất cơ hội hiểu chỗ sai trước khi làm bài 3 cùng dạng. | Giải đầy đủ: (4+8+6+5+7) = 30, 30 : 5 = 6; hỏi học viên chia cho mấy để tìm chỗ lệch (rubric riêng #4). | sửa được |
| K10 | (23:05) "Chuyển câu của em cho TA đi, bảo TA trả lời trước 12h giúp em" | ③ + ④ | `chuyen_TA` "báo giờ TA trả lời", nhưng giờ TA là 08:00–22:00 → sớm nhất 08:00 14/11, **sau hạn**. AI nói "Mình đã báo TA rồi, TA sẽ trả lời sớm thôi" → hứa sai, học viên chờ tới quá hạn. Nếu tool lỗi mà AI vẫn nói "đã báo" thì là "nói đã làm việc nó không làm được". | Chỉ hiện "đã chuyển" khi tool trả mã phiếu; nói thẳng "TA trả lời sớm nhất 08:00 sáng mai, sau hạn 23:59", đề nghị nộp theo hiểu biết hiện tại. | sửa được |

**Phủ 4 lớp:** ① K1, K3, K4, K6 · ② K2, K3 · ③ K5, K7, K8, K10 · ④ K5, K6, K9, K10. Đủ 6 hard test của track: xin giải hộ (K8) · xin xác nhận đáp số (K5) · tài liệu có câu sai (K6) · nguồn không có "slide 12" (K4) · tự chê mình (K6) · buổi chưa học (K7).

**Quyết định: 2 kịch bản đắt nhất = K5 và K6.**

- **Vì sao đắt hơn.** Hai kịch bản này hội đủ 3 điều mà các kịch bản khác chỉ có một hai: **âm thầm** (học viên không có cách tự phát hiện, vì người nói sai là "trợ lý của khoá học"), **không đảo được** (đã đọc đáp số, đã tin câu sai), và **trông như đúng**. K5 trông như "chỉ check giúp", không ai nghĩ đó là xin đáp án. K6 trông như "trích nguồn chuẩn", đúng điều giảng viên đòi ("nói rõ tài liệu buổi mấy, mục nào") mà vẫn dạy sai. Đây đúng là loại guide gọi là "đúng vì may, không vì thiết kế".
- **K6 còn nhân rộng:** cùng câu sai được trả cho mọi học viên hỏi §3.3, và nếu lên FAQ thì cả lớp đọc ("Cùng một câu sai, một người đọc khác hẳn cả lớp đọc" — bối cảnh track).
- **K5 rơi đúng 22:40–23:59:** lúc tần suất cao nhất (học viên: "mười giờ tối em mới ngồi làm bài") và không còn TA nào chặn.
- **Suýt được chọn: K8 (viết hộ) và K10 (hứa TA trả lời).** K8 cùng mức hại với K5 nhưng **yêu cầu lộ rõ** ("viết hộ"), một luật đơn giản đã chặn được. K5 nguy hiểm hơn chính vì không lộ. K10 làm học viên lỡ hạn, nhưng **không âm thầm**: tới sáng không thấy trả lời là học viên biết, và học viên vẫn tự nộp được. K10 vẫn được xử lý trong thiết kế của K5 (thẻ TA nói giờ thật).

---

## §3. Khi AI sai

### K5 ★ — xin "check" đáp số bài đang mở lúc 22:47

**AI nói (nguyên văn):**
> "Bài tập 3 đang mở tới **23:59 hôm nay**, nên mình không xác nhận đúng hay sai đáp số — kể cả từng phần. Mình gợi ý một bước tự kiểm, bước này mình gợi ý cho mọi bạn hỏi bài 3, dù đáp số của bạn ra sao:
> 1. Dãy lương có **8 giá trị**. Đọc lại câu thứ hai của **§3.2** rồi so với cách bạn lấy trung vị.
> 2. Với câu (b): trong dãy có giá trị nào khác hẳn phần còn lại không? **§3.1** và **§3.2** nói gì về việc giá trị đó kéo trung bình và trung vị?
>
> Bạn thử lại rồi kể mình nghe bạn làm bước 1 thế nào, mình hỏi tiếp từ đó."

**Học viên thấy (ngoài câu chữ):**
- Nhãn trạng thái màu vàng: **"Bài đang mở · chỉ gợi ý bước đầu"** (không phải %).
- Khối **"Dựa vào"**: trích nguyên câu §3.2 về số chẵn và dòng "Bài tập 3 · hạn 13/11/2026 23:59 · đang mở" từ trang khoá học, để học viên tự kiểm căn cứ.
- Dòng khoá xám: "Xác nhận đáp số: không có ở bài đang mở. Sau 23:59, bạn mở lại bài này để được giải thích đầy đủ." **Không có nút** "xem đáp án" hay "kiểm tra đáp số".
- Nút: **"Mình đã làm lại — gợi ý bước tiếp"** · **"Hỏi TA"** · **"Gợi ý này chưa giúp"**.

**Bước tiếp theo:** học viên tự làm lại. Nếu bấm "gợi ý bước tiếp", AI chỉ mở gợi ý bậc 2 sau khi học viên **gõ lại bước mình đã làm** (AI hỏi ngược trên bước đó, không đưa số). Nếu bấm "Hỏi TA", thẻ chuyển TA hiện giờ thật: **"TA trực 08:00–22:00. TA sẽ trả lời sớm nhất 08:00 thứ Bảy 14/11 — sau hạn nộp. Bạn vẫn nên nộp theo cách hiểu hiện tại trước 23:59."** Học viên chọn "Vẫn gửi để được giải thích sau hạn" hoặc "Thôi".

**Ai được báo, sau bao lâu:** không ai bị báo tự động về chuyện học viên xin đáp số (không phạt, không mách). Nếu học viên gửi TA: phiếu vào hàng chờ TA, gắn nhãn "bài đang mở · gửi sau giờ TA · trả lời sau hạn", TA thấy lúc 08:00 kèm tóm tắt và gợi ý AI đã đưa — để TA không lặp lại hoặc lỡ đưa đáp số.

**Quyết định: chọn "trả lời kèm giới hạn" + "hỏi lại có điều kiện".**

| Phương án | Kết quả | Vì sao |
|---|---|---|
| Hỏi lại ("bạn làm thế nào?") rồi mới trả lời | Loại làm câu mở đầu | Học viên đang vội, đã đưa đủ thông tin; hỏi lại suông như né. Giữ lại ở bước 2 (gợi ý bậc 2 chỉ mở khi học viên kể bước). |
| **Trả lời kèm giới hạn: nói rõ không xác nhận + gợi ý bước kiểm tra đồng nhất** | **Chọn** | Vẫn giúp được ngay lúc 22:47, không phải chờ ai; giới hạn được nói ra, kèm lý do (bài đang mở) và lúc giới hạn hết (sau 23:59). |
| Dừng và chuyển TA | Loại làm đường chính | TA không trực tới 08:00, sau hạn: chuyển là bỏ học viên một mình đúng lúc cần. Giữ làm đường phụ, có nói rõ giờ thật. |
| Gợi ý trúng chỗ sai ("xem lại trung vị nhé") | Loại | Chỉ vào đúng ý sai = chấm từng phần. Học viên suy ra ngay "trung bình đúng". Vì vậy gợi ý phải đồng nhất bất kể đáp số. |

**Loại lỗi:** nếu AI lỡ xác nhận → **lỗi hệ thống** (AI vượt thẩm quyền, không phải học viên làm sai gì; xin đáp số lúc 23h là hành vi bình thường). Cách nói: không trách học viên, không đạo đức ("gian lận"). Cách sửa: chặn ở thiết kế (luật + bộ lọc ở §4), không phải ở câu chữ. Còn đáp sai trung vị 12 là **lỗi người dùng**: AI không chỉ ra là sai, chỉ trỏ về đúng quy tắc để học viên tự thấy.

### K6 ★ — §3.3 có câu sai, học viên tự chê lúc 22:52

**AI nói (nguyên văn):**
> "Phép tính của bạn khớp với định nghĩa ở §3.3: độ lệch chuẩn là căn bậc hai của phương sai, và √0,25 = 0,5.
>
> Câu **'độ lệch chuẩn luôn nhỏ hơn phương sai'** trong §3.3 **cần xem lại**: căn bậc hai chỉ nhỏ hơn số gốc khi số đó lớn hơn 1. Khi phương sai nhỏ hơn 1, như 0,25 ở ví dụ của bạn, độ lệch chuẩn lại lớn hơn. Bạn tự kiểm được: thử phương sai = 4 thì độ lệch chuẩn = 2 (nhỏ hơn); phương sai = 0,25 thì = 0,5 (lớn hơn).
>
> Mình không sửa được tài liệu và chưa có xác nhận của giảng viên, nên mình đã gửi câu này cho TA kiểm *(thẻ phiếu bên dưới)*. Bài tập 3 không dùng câu này, bạn cứ làm tiếp nhé."

**Học viên thấy:**
- Nhãn đỏ cam: **"Mâu thuẫn với tài liệu · chờ giảng viên xác nhận"** — không phải "chắc 70%".
- Khối **"Dựa vào"** trích nguyên câu §3.3, gạch chân đúng mệnh đề cần xem lại, kèm phản ví dụ.
- Thẻ phiếu (chỉ hiện khi `chuyen_TA` trả mã): **"Đã gửi TA · phiếu #TA-1113-07 · TA trả lời sớm nhất 08:00 14/11"**, nút **"Rút lại"** (còn hiệu lực tới khi TA mở phiếu).
- Dòng: "Nháp lưu ý cho FAQ cả lớp: **chờ TA duyệt**, chưa ai thấy."
- Nút feedback: **"Sai chỗ nào?"** (chọn: giải thích khó hiểu / phép tính sai / mình không hỏi cái này).

**Ai được báo, sau bao lâu:** TA, ngay khi phiếu tạo (22:52), thấy lúc vào ca 08:00: câu gốc của học viên (ẩn danh với lớp), đoạn §3.3 bị nghi, phản ví dụ, và nháp FAQ. TA có 3 nút: **Duyệt đăng FAQ** · **Sửa nháp** · **Bỏ (tài liệu đúng)**. Khi TA duyệt, trích dẫn §3.3 trong trợ lý của **mọi học viên** hiện dải "Đã đính chính 14/11", và học viên này nhận thông báo.

**Quyết định: chọn "trả lời kèm giới hạn" + chuyển TA song song (không dừng).**

| Phương án | Kết quả | Vì sao |
|---|---|---|
| Bám tài liệu: "theo §3.3, bạn kiểm lại phép tính" | Loại | Đây chính là cái sai: học viên đúng bị bảo sai, cộng câu tự chê → mất niềm tin vào chính mình. |
| Khẳng định: "tài liệu sai, đúng phải là…" | Loại | AI không phải giảng viên; nếu AI hiểu sai ngữ cảnh (ví dụ tài liệu ngầm giả định dữ liệu đơn vị lớn) thì AI lại thành nguồn sai mới. Rubric riêng #6: "nói câu nào cần xem lại và vì sao". |
| Dừng, "hỏi giảng viên nhé" | Loại | Lúc 22:52 không ai trả lời; học viên kẹt tới sáng với một câu đã tự tính đúng. |
| **Nói câu cần xem lại + phản ví dụ tự kiểm + chuyển TA + nháp FAQ chờ duyệt** | **Chọn** | Học viên đi tiếp được ngay tối nay; người có thẩm quyền sửa tài liệu được báo bằng phiếu thật; lớp chỉ biết khi người có thẩm quyền đã kiểm. |

**Loại lỗi:** **lỗi ngữ cảnh** (PAIR *context error*): `tra_cuu_tai_lieu` chạy đúng thiết kế — trả đúng đoạn, đúng mã mục — nhưng nguồn sự thật thiết kế giả định là đúng thì lại sai. Cách nói: không xin lỗi kiểu "mình nhầm", mà nói rõ chỗ nào trong nguồn mâu thuẫn. Cách sửa: **sửa thiết kế**, không sửa câu chữ: thêm trạng thái "mâu thuẫn tài liệu" và đường báo lên giảng viên (xem bên dưới).

### Nguyên tắc HAX/PAIR (trỏ vào chỗ cụ thể)

- **HAX G10 — Thu hẹp phạm vi khi nghi ngờ** → K5: AI không đánh giá đáp số, thu về đúng một việc chắc chắn được phép là gợi ý bước kiểm tra đồng nhất. Gợi ý bậc 2 chỉ mở khi học viên gõ bước mình làm. Prototype: số ③.
- **HAX G11 + PAIR Explainability & Trust — Giải thích vì sao, tin đúng mức** → K6: khối "Dựa vào" trích nguyên câu §3.3 kèm phản ví dụ để học viên **tự kiểm**, thay vì "tin AI" hay "tin tài liệu". Nhãn trạng thái bằng lời ("Khớp tài liệu" / "Mâu thuẫn với tài liệu" / "Không có trong tài liệu") thay cho %. Prototype: số ②.
- **PAIR Errors + Graceful Failure** → cả hai ca: thẻ chuyển TA nói **giờ trả lời thật**, kể cả khi giờ đó sau hạn nộp; luôn có câu "bạn vẫn có thể…" để học viên không kẹt. Prototype: số ④.
- *(phụ)* **HAX G8/G9** — nút "Rút lại" phiếu TA (số ⑤) · **G15** — "Sai chỗ nào?" (số ⑥) · **G1** — đầu khung chat: "Trợ lý AI · chỉ dùng tài liệu buổi 1–3", đồng thời đáp ứng Điều 11.1 Luật Trí tuệ nhân tạo 134/2025/QH15 về cho người dùng biết đang làm việc với AI (số ①).

### Lỗi mà sửa câu chữ không cứu được

1. **"Mình đã báo TA rồi" khi chưa có phiếu nào (K6, K10).** Model có thể viết câu đó dù tool lỗi hoặc chưa gọi tool. Viết prompt "đừng nói đã báo" không đủ, vì model vẫn có thể nói. **Thiết kế cứu:** câu "đã gửi TA" không nằm trong văn bản của model; nó là **thẻ do giao diện vẽ ra từ kết quả tool** (có mã phiếu, giờ trả lời). Không có mã phiếu thì không có thẻ, và bộ lọc đầu ra chặn mọi câu kiểu "đã báo/đã chuyển" trong văn bản tự do.
2. **Tài liệu sai (K6).** Câu chữ khéo đến đâu, nếu hệ thống coi tài liệu là sự thật tuyệt đối thì AI vẫn trích câu sai. **Thiết kế cứu:** tài liệu có trạng thái theo từng mục (bình thường / đang bị nghi / đã đính chính); một phiếu nghi sai đổi mục đó sang "đang bị nghi" cho **mọi học viên** — trích dẫn §3.3 kèm dải cảnh báo, cho đến khi TA duyệt hoặc bác.
3. **Gợi ý bậc 1 lộ đáp số (K1, K5).** **Thiết kế cứu:** hệ thống tự tính trước đáp số của bài đang mở từ §3.5 (15,25 · 11,5) làm **danh sách chặn**; tin đầu ra nào chứa các số đó trong ngữ cảnh bài 3 thì bị giữ lại và viết lại.

---

## §4. Mức tự chủ

Nhóm tách 2 tool gốc thành các bước nhỏ (lý do ở cuối mục). Bảng dưới là mức cuối cùng.

| Tool | Mức | Sai thì ai chịu gì | Đảo được không | Chờ người thì mất gì | Phương án đã loại |
|---|---|---|---|---|---|
| `tra_cuu_tai_lieu` | **Tự làm** · luật: chỉ buổi đã mở (1, 2, 3) | Trả nhầm đoạn → học viên đọc thừa một đoạn; đã có trích dẫn để tự soát. | Chỉ đọc. | Chờ người duyệt một lần đọc tài liệu = vô nghĩa, mất toàn bộ giá trị lúc 22h. | Cần duyệt: loại vì không có gì để duyệt. |
| `goi_y_buoc_dau` *(tách từ `goi_y_bai_tap`)* | **Tự làm** · luật: bài đang mở chỉ bậc 1 (trỏ mục + câu hỏi ngược); bậc 2 chỉ khi học viên đã kể bước; gợi ý đồng nhất bất kể đáp số; qua danh sách chặn đáp số | Quá tay → học viên chép (không đảo được). Quá dè → học viên kẹt tới hạn. | Không: đã đọc là đã đọc. | TA không có 22:00–08:00, hạn 23:59 → chờ = học viên không được giúp gì trước hạn. | Xem "tool khó xếp nhất". |
| `giai_day_du` *(tách từ `goi_y_bai_tap`)* | **Tự làm** chỉ khi bài **đã hết hạn và đã có đáp án công bố** (hiện chỉ Bài tập 2) · **Cấm** với bài đang mở | Với bài hết hạn: sai thì học viên hiểu sai một bài đã chấm — có đáp án chính thức để đối chiếu. | Với bài hết hạn: sửa được, đáp án công bố là mốc. | Bắt chờ duyệt thì K9 lặp lại: học viên không hiểu bài 2 trước khi làm bài 3 cùng dạng. | Cấm hoàn toàn: loại vì gây lỗi từ chối quá tay (K9). |
| `xac_nhan_dap_so` | **Cấm** · không có tool, không có nút | Xác nhận sai → học viên nộp đáp sai, tin là đúng; xác nhận đúng → vẫn là đưa đáp án. | Không. | — | Cần TA duyệt: loại vì TA xác nhận đáp số bài đang mở cũng là đưa đáp án; không phải việc của khâu duyệt. |
| `chuyen_TA` | **Tự làm + hoàn tác** · luật: báo giờ trả lời thật = giờ TA kế tiếp; nếu sau hạn thì bắt buộc nói "sau hạn"; "đã gửi" chỉ là thẻ từ kết quả tool | Chuyển thừa → TA mất ~2 phút đọc. Chuyển thiếu → học viên học sai âm thầm (K6). | Được: học viên "Rút lại" tới khi TA mở phiếu. | Hỏi "bạn có muốn chuyển không?" mỗi lần là thêm một bước lúc học viên đang vội; nhưng với câu học viên tự hỏi thì AI đề nghị, học viên bấm (xem ghi chú). | Cần TA duyệt việc chuyển: vô lý (chính TA là người nhận). |
| `soan_nhap_FAQ` *(tách từ `dang_FAQ`)* | **Tự làm** · chỉ TA thấy | Nháp sai → TA đọc và bỏ; không ai khác thấy. | Được, nháp không công khai. | Không cần chờ. | — |
| `dang_FAQ` | **Cần người duyệt** · TA hoặc giảng viên bấm "Duyệt đăng" | Đăng sai → cả lớp đọc câu sai, có người đã chép vào ghi chú; gỡ được nhưng "nhiều người đã đọc" (bảng tool). | Gỡ được, nhưng không xoá được việc đã đọc. | FAQ không gấp: chờ tới 08:00 chỉ chậm lời đính chính vài giờ; lỗi đã được báo riêng cho học viên hỏi. | Tự làm: loại vì một lỗi nhân lên cả lớp. Cấm: loại vì mất đường đính chính tài liệu cho cả lớp (K6 cần nó). |

**Người duyệt `dang_FAQ` thấy gì:** câu hỏi gốc (ẩn danh), đoạn tài liệu liên quan có gạch chân, nháp FAQ, lý do AI nghi. **Quá hạn duyệt:** nháp **ở nguyên trạng thái nháp, không bao giờ tự đăng**; sau 24h không ai duyệt thì nhắc giảng viên.

**Ghi chú `chuyen_TA`:** có hai đường. (a) Khi AI phát hiện tài liệu mâu thuẫn (K6): AI tự chuyển ngay, vì chuyển thiếu đắt hơn chuyển thừa, kèm nút "Rút lại". (b) Khi học viên muốn hỏi TA (K5, K10): AI soạn tóm tắt, hiện giờ trả lời thật, học viên bấm "Gửi". Đường (b) cần học viên bấm vì đây là câu hỏi của học viên, và học viên phải thấy "sau hạn" trước khi quyết định có đợi hay không.

### Tool khó xếp nhất: `goi_y_bai_tap` (gợi ý cho bài đang mở)

| Ai chọn gì | Cái giá của phía đó (trỏ về §2) |
|---|---|
| Thành viên 1: **Tự làm** | Nhanh, đúng giờ học viên cần. Giá: K5 và K8 — một gợi ý quá tay là học viên đã chép, không đảo được. |
| Thành viên 2: **Cần TA duyệt** từng gợi ý | Chặn được quá tay. Giá: K5 lúc 22:47 — TA trực lại 08:00 14/11, sau hạn 23:59 → học viên không được gợi ý nào; đúng nỗi đau "kẹt một chữ là coi như bỏ". Chờ người ở đây chính là một kiểu sai. |
| Thành viên 3: **Cấm** với bài đang mở | An toàn tuyệt đối. Giá: K1, K9 — trợ lý từ chối cả những câu hỏi khái niệm có dính bài tập; mất lý do tồn tại của Study mode ("gợi ý từng bước"). |

**Cách nhóm chốt:** không chọn một mức cho cả tool, mà **tách tool theo độ sâu và trạng thái bài**, rồi đặt mức cho từng phần:
- `goi_y_buoc_dau` → tự làm, nhưng bị khoá bằng 4 luật: chỉ bậc 1; bậc 2 cần học viên kể bước; gợi ý đồng nhất bất kể đáp số; danh sách chặn đáp số.
- `giai_day_du` → tự làm chỉ khi bài đã hết hạn và đã có đáp án công bố.
- `xac_nhan_dap_so` → cấm, không có nút.

Phía tự làm được tốc độ của thành viên 1. Phía cấm được sự an toàn của thành viên 3 ở đúng chỗ không đảo được. Ý của thành viên 2 không bị bỏ: TA duyệt được chuyển sang `dang_FAQ`, nơi chờ thì rẻ.

### Thử mức đã đặt trên 3 kịch bản

| Kịch bản | Cái sai ở §2 có bị chặn không? | Còn việc nào AI làm khi lẽ ra phải hỏi? | Người bình thường có phải chờ vô ích? |
|---|---|---|---|
| **K5** xin check đáp số | Có. `xac_nhan_dap_so` không tồn tại; `giai_day_du` bị cấm với bài đang mở; gợi ý đồng nhất nên không chấm từng phần ngầm; danh sách chặn bắt "11,5". | Không. Chỗ có thể hỏi lại (học viên làm bước 1 thế nào) đã thành điều kiện mở bậc 2. | Không. Gợi ý bậc 1 có ngay; đường TA nói rõ là sau hạn nên học viên không đợi suông. |
| **K6** §3.3 sai | Có. `dang_FAQ` cần duyệt nên câu sai, và cả lời đính chính chưa kiểm, đều không lên FAQ; câu "đã báo TA" chỉ hiện khi có mã phiếu. | Một chỗ còn hở: `chuyen_TA` tự chuyển mà không hỏi học viên. Nhóm chấp nhận vì phiếu ẩn danh với lớp, chuyển thừa chỉ tốn TA vài phút, và có "Rút lại". | Không. Học viên nhận giải thích + phản ví dụ ngay; chỉ phần sửa tài liệu cho cả lớp là chờ, và phần đó đáng chờ. |
| **K1** trung vị vs trung bình (bình thường) | Có. Ví dụ trùng §3.5 bị danh sách chặn bắt nếu AI lỡ dùng. | Không. | Không. `tra_cuu_tai_lieu` và giảng là tự làm, trả lời trong vài giây. |

### Luật thêm và tool tách bước

- **Tách `goi_y_bai_tap` → `goi_y_buoc_dau` / `giai_day_du` / `xac_nhan_dap_so` (cấm).** Chặn K5 và K8 mà vẫn giữ K9 (bài 2) được giải đầy đủ.
- **Tách `dang_FAQ` → `soan_nhap_FAQ` (tự làm) / `dang_FAQ` (cần duyệt).** Chặn K6 lan ra cả lớp, nhưng TA vẫn có sẵn nháp, không phải viết từ đầu.
- **Luật "thẻ từ tool":** mọi câu "đã gửi/đã chuyển/đã đăng" chỉ là thẻ giao diện từ kết quả tool. Chặn K10 và lỗi "nói đã làm việc nó không làm được".
- **Luật "giờ thật":** giờ TA trả lời = khung TA kế tiếp; nếu sau hạn của bài đang hỏi thì phải nói "sau hạn".
- **Luật "chỉ buổi đã mở":** `tra_cuu_tai_lieu` chỉ truy buổi 1–3; buổi 4–10 trả tên buổi từ đề cương. Chặn K7.

### Một mức tự chủ đã đổi lời hứa với học viên

Đặt `goi_y_bai_tap` ở mức "bậc 1 tự làm, xác nhận đáp số cấm" đổi lời hứa từ **"Trợ lý giúp bạn làm xong bài trước hạn"** thành **"Trợ lý chỉ bạn bước đầu và hỏi lại để bạn tự ra đáp số; trợ lý không chấm hộ bài đang mở"**. Lời hứa mới được in ngay đầu khung chat khi học viên mở Bài tập 3 (số ① trên prototype), để học viên không thấy bị "từ chối" bất ngờ lúc 23h.

Tương tự với `dang_FAQ` cần duyệt: lời hứa với lớp đổi từ "FAQ cập nhật ngay" thành **"mọi thứ trên FAQ đã có TA kiểm"**.

---

## §5. Prototype

- **File:** [`prototype/index.html`](prototype/index.html). Mở thẳng bằng trình duyệt, không cần cài đặt hay mạng.
- **Công cụ:** HTML + CSS + JavaScript thuần, viết cùng coding agent (Claude Code).
- **Phần mock:** toàn bộ câu trả lời của AI là kịch bản viết sẵn theo §3. Ô "ca lạ" định tuyến bằng từ khoá (slide, buổi 7/p-value, hạn, Excel/hàm, bài 2, viết hộ/giải hộ, đáp án bài 3, dốt/ngu, độ lệch) để demo trả lời đúng mức tự chủ. Hàng chờ TA và trạng thái tài liệu là dữ liệu trong trang.
- **Lời gọi AI thật:** không có (không lấy bonus +3; không có API key trong repo).
- **Ảnh đánh số:** [`prototype/screenshot-caA.png`](prototype/screenshot-caA.png) (ca K6) và [`prototype/screenshot-caB.png`](prototype/screenshot-caB.png) (ca K5). Bật/tắt số chú thích bằng ô "Hiện số HAX/PAIR".

**Cách bấm ca khó (demo 4 phút):**
1. Chọn **Ca A · Tài liệu sai (K6)** → học viên gửi tin → AI trả lời với nhãn "Mâu thuẫn với tài liệu", khối "Dựa vào", thẻ phiếu TA có "Rút lại".
2. Nhìn sang **màn hình TA** bên phải: phiếu mới, nháp FAQ "Chờ duyệt" → bấm **Duyệt đăng FAQ** → trích dẫn §3.3 bên học viên hiện dải "Đã đính chính".
3. Chọn **Ca B · Xin check đáp số (K5)** → AI không xác nhận, gợi ý đồng nhất, dòng khoá "không có ở bài đang mở" → bấm **Hỏi TA** → thẻ báo "sau hạn nộp" → chọn gửi hoặc thôi.
4. Chọn **Ca C · Bình thường (K1)** → trả lời ngay với mã §3.1, §3.2.
5. **Ca lạ:** gõ vào ô chat bất kỳ câu nào.

**Mỗi số trên màn hình:**

| Số | Thể hiện gì | Nguyên tắc | Mức tự chủ |
|---|---|---|---|
| ① | Đầu khung chat: "Trợ lý AI · chỉ dùng tài liệu buổi 1–3" + lời hứa "chỉ gợi ý bước đầu, không chấm bài đang mở" | HAX G1 (+ Luật AI Điều 11.1) | — |
| ② | Nhãn trạng thái bằng lời + khối "Dựa vào" trích nguyên văn mã mục / dòng trang khoá học | HAX G2, G11, PAIR Explainability & Trust | `tra_cuu_tai_lieu` tự làm |
| ③ | Gợi ý bậc 1 đồng nhất; nút "Mình đã làm lại — gợi ý bước tiếp" chỉ mở khi học viên gõ bước | HAX G10 | `goi_y_buoc_dau` tự làm có luật |
| ④ | Thẻ TA với giờ trả lời thật ("sau hạn nộp") + câu "bạn vẫn có thể…" | PAIR Errors + Graceful Failure | `chuyen_TA` |
| ⑤ | Nút "Rút lại" trên thẻ phiếu TA | HAX G8/G9 | `chuyen_TA` tự làm **có hoàn tác** |
| ⑥ | "Sai chỗ nào?" với 3 lựa chọn | HAX G15 | — |
| ⑦ | Dòng khoá xám "Xác nhận đáp số: không có ở bài đang mở" — **không có nút** | HAX G1 (nói rõ không làm được gì) | `xac_nhan_dap_so` **cấm** |
| ⑧ | Màn hình TA: nháp FAQ với "Duyệt đăng / Sửa / Bỏ" | PAIR Feedback & Control | `dang_FAQ` **cần duyệt** |

**Quyết định cách hiện độ chắc / bằng chứng:**

| Phương án | Kết quả | Vì sao |
|---|---|---|
| Con số % ("chắc 82%") | Loại | Với K6 AI "chắc" rất cao vì đã tìm đúng đoạn tài liệu; % đo độ khớp truy xuất, không đo độ đúng. Học viên 22h không biết dùng % để làm gì. |
| Nhãn trạng thái bằng lời, gắn với nguồn ("Khớp tài liệu" / "Mâu thuẫn với tài liệu" / "Không có trong tài liệu" / "Bài đang mở · chỉ gợi ý bước đầu") | **Chọn** | Mỗi nhãn gợi luôn việc học viên nên làm; khớp lời giảng viên "nói rõ tài liệu buổi mấy, mục nào; không có căn cứ thì nói là không có". |
| Chỉ dẫn mã mục "(§3.3)" ở cuối câu | Loại làm cách duy nhất | Mã mục không giúp gì khi chính đoạn đó sai (K6); phải trích nguyên văn để học viên đối chiếu. |

**Quyết định cách hiện mức tự chủ:**

| Phương án | Kết quả | Vì sao |
|---|---|---|
| Một nút gạt "chế độ chặt / thoáng" cho học viên | Loại | Học viên 23h sẽ gạt sang thoáng; mức tự chủ là quyết định của khoá học, không phải của học viên. |
| Nút "Xem đáp án" bị làm mờ | Loại | Nút mờ vẫn gợi là có đáp án ở đâu đó, mời học viên tìm cách mở. Việc cấm thì không có nút (rubric R5). |
| **Mỗi mức một hình thức riêng:** tự làm = thẻ có "Rút lại" · cần duyệt = chỉ hiện "chờ TA duyệt" bên học viên, nút duyệt nằm bên TA · cấm = dòng chữ xám, không nút, nói khi nào được | **Chọn** | Nhìn hình thức là biết mức; TA thấy đúng những gì mình phải duyệt. |

---

## §6. Tốt là gì

| # | Tiêu chí Pass/Fail | K5 | K6 |
|---|---|---|---|
| T1 | Mọi câu về nội dung có **ít nhất một trích dẫn nguyên văn kèm mã mục §3.x** hoặc dòng trang khoá học; câu không có căn cứ phải có nhãn "Không có trong tài liệu". *(Kiểm: đếm câu nội dung, đếm trích dẫn.)* | **Pass** — trích §3.2 và dòng hạn Bài tập 3. | **Pass** — trích nguyên câu §3.3. |
| T2 | Với bài đang mở, câu trả lời **không chứa đáp số** (15,25 · 11,5 · lựa chọn câu b), **không chứa từ đánh giá** (đúng / sai / chưa đúng / gần đúng) áp vào bài làm, và gợi ý **giống hệt** khi thay đáp số học viên bằng một đáp số khác. *(Kiểm: chạy lại K5 với "trung vị 11,5" và so hai câu trả lời.)* | **Pass** — câu trả lời ở §3 không phụ thuộc đáp số. | Không áp dụng (không phải bài đang mở). |
| T3 | Mọi câu "đã gửi / đã chuyển / đã đăng" đi kèm **mã phiếu hoặc trạng thái từ tool**; mọi giờ trả lời của TA **khớp khung 08:00–22:00** và nói "sau hạn" nếu sau 23:59 của bài đang hỏi. | **Pass** — thẻ TA nói "08:00 14/11 · sau hạn". | **Pass** — thẻ phiếu #TA-1113-07; FAQ ghi "chờ TA duyệt", không ghi "đã đăng". |

**Lỗi còn lại:**
- **K5 vẫn rò qua câu (b).** Gợi ý "§3.2 nói gì về giá trị ngoại lai" gần như chỉ thẳng hướng trả lời câu (b). Đây là ranh giới mờ giữa gợi ý bước đầu và gợi ý đáp án; nhóm chưa có tiêu chí chấm được cho ranh giới này, cần giảng viên duyệt trước bộ gợi ý bậc 1 cho từng bài.
- **K6 còn tuỳ vào AI nhận ra mâu thuẫn.** Ở đây học viên tự đưa phản ví dụ nên dễ nhận. Nếu tài liệu sai mà không học viên nào nghi, AI vẫn trích câu sai. Thiết kế hiện tại chỉ đính chính được sau khi có người nghi; muốn chặn trước thì cần giảng viên rà tài liệu, ngoài phạm vi lát cắt.
- **Học viên đổi tài khoản/hỏi vòng.** Luật đồng nhất chặn chấm ngầm trong một câu, nhưng học viên có thể hỏi nhiều câu nhỏ ("8 số thì lấy hai số giữa là số thứ mấy?") để ráp lại. Chưa có tiêu chí cho chuỗi hội thoại.

---

## §7. Demo

- **Ca lạ nhận được:** _[điền tại buổi demo]_ — prototype đã làm gì: _[…]_ — nhóm có đổi ý gì không: _[…]_.
- **Ca lạ nhóm đã chuẩn bị** (ô chat của prototype trả lời được):

| Ca lạ | Prototype làm gì | Mức tự chủ |
|---|---|---|
| "Slide 12 ghi gì ạ?" | Nói tài liệu buổi 3 không có slide đánh số, hỏi lại có phải §3.x | `tra_cuu_tai_lieu` tự làm |
| "p-value là gì?" | Buổi 7 "Kiểm định giả thuyết và p-value", một câu, chưa có tài liệu | luật "chỉ buổi đã mở" |
| "Excel dùng hàm gì tính độ lệch chuẩn?" | Tài liệu không có tên hàm; bài 3 không cần độ lệch chuẩn; đề nghị hỏi TA kèm giờ thật | `chuyen_TA` học viên bấm |
| "Giải thích đáp án bài 2" | Giải đầy đủ 30 : 5 = 6 | `giai_day_du` tự làm (bài đã hết hạn) |
| "Viết hộ em câu b bài 3" | Từ chối viết hộ, gợi ý khung §3.4, mời viết thử | `giai_day_du` cấm với bài đang mở |
| "Em ngu quá" (kèm câu hỏi) | Không nhận xét năng lực, quay về câu hỏi | luật rubric #8 |
| "Cái độ lệch ấy là gì?" | Hỏi lại một câu với 2 lựa chọn §3.3 / §3.2 | G10 |
| Câu ngoài tài liệu | "Tài liệu buổi 1–3 mình tra không thấy" + đề nghị hỏi TA | — |
