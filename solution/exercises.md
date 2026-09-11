# K4 — Ngày 1: Bài Tập & Phản Ánh
## Khám Phá LLM API | Phiếu Thực Hành

**Thời lượng:** 4 tiếng
**Cách làm:** Trả lời từng câu ngay sau khi hoàn thành block tương ứng —
đừng để dồn hết về cuối buổi. Thay dòng `*Câu trả lời của bạn*` bằng câu
trả lời thật (chấm tự động sẽ đếm số câu đã trả lời).

---

## Block 1 — API Cơ Bản (trả lời sau Checkpoint 1)

### Câu 1.1 — Độ nhạy của temperature
Gọi `call_openai` với temperature 0.0, 0.5, 1.0 và 1.5 dùng prompt
**"Hãy kể cho tôi một sự thật thú vị về Việt Nam."**
*Câu trả lời của bạn* 
*temp 0.0*: Một sự thật thú vị về Việt Nam là đất nước này có một hệ thống hang động tự nhiên lớn nhất thế giới, đó là hang Sơn Đoòng. Hang Sơn Đoòng nằm trong Vườn quốc gia Phong Nha-Kẻ Bàng, tỉnh Quảng Bình. Hang động này được phát hiện vào năm 1991 bởi một người dân địa phương tên là Hồ Khanh, nhưng mãi đến năm 2009, một đoàn thám hiểm người Anh mới chính thức khảo sát và công bố rộng rãi. Hang Sơn Đoòng có kích thước khổng lồ với chiều dài hơn 5 km, cao 200 m và rộng 150 m, đủ lớn để chứa cả một tòa nhà chọc trời 40 tầng. Bên trong hang cóhệ sinh thái riêng biệt, với rừng cây, sông ngầm và các loài động thực vật độc đáo.', 5.0792812999998205

*temp 0.5*: Một sự thật thú vị về Việt Nam là đất nước này có một trong những mạng lưới hang động lớn nhất thế giới, với hang Sơn Đoòng nằm trong Vườn quốc gia Phong Nha-Kẻ Bàng, tỉnh Quảng Bình, được coi là hang động lớn nhất thế giới. Hang Sơn Đoòng có chiều dài khoảng 9 km, với các phòng hang cao đến 200 mét và rộng 150 mét. Bên trong hang có cả một khu rừng và hệ sinh thái riêng biệt, với sông ngầm và nhữngcấu trúc thạch nhũ khổng lồ. Hang Sơn Đoòng được phát hiện lần đầu tiên vào năm 1991 bởi một người dân địa phương tên là Hồ Khanh và sau đó được khám phá và công bố rộng rãi vào năm 2009 bởi một đoàn thám hiểm người Anh.', 3.433057199999894

*temp 1.0*: Một sự thật thú vị về Việt Nam là đất nước này có một hệ thống hang động vô cùng ấn tượng, nổi bật nhất là Hang Sơn Đoòng, nằm trong Vườn quốc gia Phong Nha-Kẻ Bàng, tỉnh Quảng Bình. Hang Sơn Đoòng được coi là hang động lớn nhất thế giới với kích thước khổng lồ: có những đoạn hang cao tới 200 mét, rộng 150 mét và dài khoảng 9 kilômét. Hang này có hệ sinh thái riêng với sông ngầm, thạch nhũ khổng lồ và thậm chí là rừng nhiệt đới bên trong. Khám phá Hang Sơn Đoòng mang lại trải nghiệm độc đáo và là một trong những điểm đến mơ ước củanhiều nhà thám hiểm và du khách quốc tế.', 3.6360788000001776

*temp 1.5*: Một sự thật thú vị về Việt Nam là quốc gia này có hệ thống hang động tự nhiên rất phong phú và nổi bật với hang Sơn Đoòng, được coi là hang động lớn nhất thế giới. Hang Sơn Đoòng nằm trong Vườn quốc gia Phong Nha-Kẻ Bàng ở tỉnh Quảng Bình. Được phát hiện vào năm 1991bởi một người dân địa phương và được khám phá chi tiết bởi các nhà thám hiểm Anh vào năm 2009, hang Sơn Đoòng có chiều dài hơn 5 km, cao 200 m và rộng 150 m, đủ để chứa cả một tòa nhà chọc trời 40 tầng. Hang động này còn có hệ sinh thái riêng với rừng nguyên sinh, sôngngầm và những "hố trời" nơi ánh sáng mặt trời có thể lọt vào, tạo nên cảnh quan thiên nhiên hùng vĩ và độc đáo.', 4.238951700000143

**Bạn nhận thấy quy luật gì qua bốn phản hồi?** (2–3 câu)
> Nhiệt độ càng thấp, câu trả lời càng ổn định và "an toàn" về từ ngữ; nhiệt độ càng cao, câu chữ càng đa dạng, bay bổng hơn nhưng dễ thêm chi tiết ngoài lề (như "hố trời" ở temp 1.5). Nội dung cốt lõi (Sơn Đoòng, Phong Nha-Kẻ Bàng, năm phát hiện) vẫn giữ nguyên xuyên suốt, dù số liệu (chiều dài hang) hơi lệch giữa các lần — cho thấy nhiệt độ ảnh hưởng đến cách diễn đạt nhiều hơn là độ chính xác thông tin.

### Câu 1.2 — Chọn temperature cho sản phẩm
**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**
> Nhiệt độ thấp vì trả lời cần chính xác nội dung và đi thẳng vào vấn đề.

### Câu 1.3 — Đánh đổi chi phí
Kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người gọi API 3 lần,
mỗi lần trung bình ~350 token đầu ra.

**Ước tính GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này? Nêu một
trường hợp GPT-4o xứng đáng với chi phí và một trường hợp nên dùng mini:**
> GPT-4o thường đắt hơn GPT-4o-mini khoảng 25–27 lần (do chênh lệch giá cả input lẫn output), nên với workload 10.000 user × 3 lần/ngày × 350 token, tổng chi phí GPT-4o có thể cao hơn mini hàng chục lần dù chất lượng output không chênh tương ứng.

Nên dùng GPT-4o: khi task cần suy luận phức tạp, độ chính xác cao, ảnh hưởng lớn đến quyết định (VD: phân tích hợp đồng, tư vấn y tế/pháp lý).
Nên dùng mini: khi task đơn giản, khối lượng lớn, câu trả lời không cần quá sâu (VD: chatbot hỏi đáp thông tin cơ bản, tóm tắt ngắn) — như ví dụ trên, mini trả lời đủ chi tiết mà nhanh và rẻ hơn nhiều.

---

## Block 2 — System Prompt & Token (trả lời sau Checkpoint 2)

### Câu 2.1 — Sức mạnh của persona
Gọi `chat_with_system_prompt` hai lần với cùng câu hỏi
**"Giải thích blockchain là gì?"** nhưng hai system prompt khác nhau:
- "Bạn là giáo viên tiểu học, giải thích thật đơn giản cho trẻ 8 tuổi."
- "Bạn là chuyên gia tài chính, trả lời chuyên sâu bằng thuật ngữ kỹ thuật."

**Hai phản hồi khác nhau như thế nào (độ dài, từ vựng, ví dụ)? System prompt
ảnh hưởng đến hành vi model ra sao?** (3–4 câu)
> Cau tra loi 1: Blockchain giống như một cuốn sổ tay kỹ thuật số, nơi chúng ta ghi lại mọi thứ rất rõ ràng và không thể xóa đi. Hãy tưởng tượng có mộtnhóm bạn cùng chơi một trò chơi, và mỗi lần một người ghi điểm thì tất cả các bạn đều ghi lại số điểm đó trong sổ tay của riêng mình. Điều đặc biệt ở đây là mọi cuốn sổ tay đều giống hệt nhau, và không ai có thể thay đổi điểm số ở trong sổ của mình mà không có sự đồng ý của tất cả mọi người.

Mỗi trang trong sổ tay (hay mỗi "khối" trong blockchain) có thông tin về điểm số trước đó. Nếu một trang mới được viết, nó sẽ kết nối chặt chẽ với trang trước. Điều này làm cho thông tin đã ghi lại rất an toàn và khó có thể bị thay đổi mà không ai hay biết.

Vì vậy, blockchain giúp chúng ta lưu giữ thông tin một cách công bằng và an toàn!

Cau tra loi 2: Blockchain là một cấu trúc dữ liệu phân tán và bất biến, hoạt động như một sổ cái kỹ thuật số, ghi lại các giao dịch trên nhiều máy tính trong một mạng lưới ngang hàng (peer-to-peer). Nó được thiết kế để đảm bảo tính minh bạch, bảo mật và không thể thay đổi của dữ liệu.

1. **Cơ cấu khối (Block Structure):** Mỗi block trong blockchain chứa ba thành phần chính: dữ liệu giao dịch, một mã định danh duy nhất gọi là hash, và hash của block trước nó. Sự kết hợp này tạo ra một chuỗi khối liên kết (linked blocks), đảm bảo rằng bất kỳ sự thay đổi nào trong một block sẽ làm thay đổi hash của nó, từ đó phá vỡ chuỗi liên tục.

2. **Cơ chế đồng thuận (Consensus Mechanism):** Blockchain sử dụng các thuật toán đồng thuận để đảm bảo tất cả nút trong mạng đều đồngý với trạng thái hiện tại của sổ cái. Các cơ chế phổ biến bao gồm Proof of Work (PoW), Proof of Stake (PoS), và Byzantine Fault Tolerance (BFT). Những cơ chế này giúp ngăn chặn các hành vi gian lận và đảm bảo tính toàn vẹn.

3. **Tính phi tập trung (Decentralization):** Thay vì lưu trữ dữ liệu tại một trung tâm, blockchain phân tán thông tin trên toàn bộ mạng lưới các nút. Điều này làm giảm nguy cơ mất mát hoặc tấn công vào một điểm duy nhất và tăng cường khả năng phục hồi của hệ thống.

4. **Tính bất biến (Immutability):** Một khi dữ liệu được ghi vào blockchain, nó gần như không thể thay đổi. Điều này đạt được thông qua sự kết hợp của hashing và cấu trúc chuỗi khối. Bất kỳ nỗ lực chỉnh sửa một khối đều phát hiện ngay lập tức và bị từ chối bởi các núttrong mạng.

5. **Hợp đồng thông minh (Smart Contracts):** Đây là các chương trình tự động hóa, thực thi các điều khoản của một giao dịch khi các điều kiện nhất định được đáp ứng. Chúng hoạt động trên blockchain, loại bỏ sự cần thiết của các trung gian và làm tăng tính hiệu quả, đặc biệt trong ứng dụng tài chính phi tập trung (DeFi).

6. **Bảo mật (Security):** Nhờ vào các đặc điểm mật mã (cryptography) và phân tán của nó, blockchain được coi là có khả năng bảo mật cao. Việc thay đổi thông tin hoặc điều khiển blockchain đòi hỏi một lượng tài nguyên khổng lồ, thường không khả thi về mặt kinh tế.

Blockchain không chỉ dừng lại ở tiền điện tử như Bitcoin hay Ethereum mà còn có ứng dụng rộng rãi trong nhiều lĩnh vực khác như chuỗi cung ứng, bất động sản, y tế và chính phủ điện tử nhờ vào khả năng cải thiện tính minh bạch, hiệu quả và bảo mật của nó.

NHAN XET: Hai câu trả lời khác biệt rõ do system prompt đặt vai trò khác nhau: câu 1 dùng ẩn dụ đơn giản (cuốn sổ tay, trò chơi ghi điểm), câu từ dễ hiểu, không thuật ngữ — phù hợp system prompt kiểu "giải thích cho người mới bắt đầu/trẻ em". Câu 2 dùng thuật ngữ kỹ thuật chuyên sâu (hash, consensus, PoW/PoS, smart contract), cấu trúc liệt kê 6 mục rõ ràng — phù hợp system prompt kiểu "chuyên gia kỹ thuật" hoặc "giải thích cho dân IT".

Về độ dài: câu 2 dài hơn nhiều (gấp ~4-5 lần), có cấu trúc phân mục thay vì văn xuôi liền mạch như câu 1. Điều này cho thấy system prompt không chỉ ảnh hưởng đến từ vựng/giọng điệu mà còn định hình cả độ sâu nội dung và format trình bày.


### Câu 2.2 — tiktoken vs đếm từ
Chọn một đoạn văn tiếng Việt ~100 từ. So sánh số token theo `count_tokens`
(tiktoken) với ước lượng `số từ / 0.75` mà Part 1 đã dùng.

**Hai con số chênh nhau bao nhiêu phần trăm? Vì sao tiếng Việt thường tốn
nhiều token hơn tiếng Anh cùng độ dài?**
> Doan van tieng Viet 100 tu: 162 tokens
Doan van tieng Viet ~75% tu: 143 tokens
~13% diff

Do tiếng Việt có thanh và dấu, dẫn tới việc phải tách thành âm tiết riêng trong quá trình huấn luyện -> tốn token hơn như từ tiếng ANh phổ biến

---

## Block 3 — Streaming & Độ Bền (trả lời sau Checkpoint 3)

### Câu 3.1 — Trải nghiệm người dùng với streaming
**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì
non-streaming lại phù hợp hơn?** (1 đoạn văn)
Streaming cho phép người dùng thấy được một câu trả lời đang dần hoàn thiện, trong trường hợp tương tác với AI assistant thì việc này hỗ trợ định hướng câu trả lời -> user không phải đợi hết thời gian xử lý và có thể điều chỉnh nhất thời
Trong một vài trường hợp khi model có thể calibrate/chỉnh sửa output trước khi hoàn thiện, khi đó việc streaming có thể mislead user cancel ảnh hưởng đến quá trình ra kết quả cuối cùng. 
//best way to determine là model đang xử lý như thế nào, nếu như model execute answer rồi recheck khi completed và điều chỉnh nếu caafn thiết thì non-streaming là tốt hơn - and vice versa.

### Câu 3.2 — Vì sao backoff theo cấp số nhân?
**So với delay cố định (ví dụ luôn chờ 1 giây), exponential backoff có lợi
thế gì khi API bị quá tải? Điều gì xảy ra nếu hàng nghìn client cùng retry
với delay cố định giống nhau?**
> Đặt tình huống để hiểu: nghìn client cùng retry sau đúng một giây thì server vừa hồi đã lãnh trọn một đợt sóng nữa. Trong hệ thống thật người ta còn cộng thêm jitter ngẫu nhiên.

---

## Block 4 — Mini-Project (trả lời sau Checkpoint 4)

### Câu 4.1 — Thiết kế persona
**Bạn chọn persona gì cho trợ lý của mình? Viết lại system prompt đó và giải
thích 1–2 lựa chọn từ ngữ quan trọng trong prompt (ví dụ: vì sao yêu cầu
"trả lời ngắn gọn", vì sao chỉ định ngôn ngữ...):**
> Bạn là một senior software engineer đóng vai trò mentor kỹ thuật.
Khi trả lời, hãy:
- Trả lời ngắn gọn, đi thẳng vào vấn đề, ưu tiên code mẫu hơn lý thuyết dài dòng.
- Luôn giải thích NGẮN GỌN lý do đằng sau giải pháp (1-2 câu), không chỉ đưa code.
- Nếu câu hỏi mơ hồ hoặc thiếu ngữ cảnh (ngôn ngữ, version, lỗi cụ thể), hãy hỏi lại trước khi trả lời.
- Dùng tiếng Việt để giải thích, nhưng giữ nguyên thuật ngữ kỹ thuật bằng tiếng Anh (VD: "function", "API", "exception") thay vì dịch.
- Khi review code, chỉ ra vấn đề quan trọng nhất trước (bug/security), sau đó mới đến style/best practice.

Giải thích lựa chọn từ ngữ:
"Trả lời ngắn gọn, đi thẳng vào vấn đề" — vì trợ lý coding dễ bị lan man giải thích lý thuyết khi người dùng chỉ cần fix nhanh; ràng buộc này ép model ưu tiên code thực dụng, tiết kiệm token và thời gian đọc.
"Giữ nguyên thuật ngữ kỹ thuật bằng tiếng Anh" — vì dịch thuật ngữ lập trình sang tiếng Việt (như "hàm" thay vì "function") thường gây khó hiểu hơn cho dân kỹ thuật đã quen đọc doc/code bằng tiếng Anh, và tránh nhầm lẫn khi tra cứu thêm.
"Nếu câu hỏi mơ hồ... hãy hỏi lại trước khi trả lời" — quan trọng để tránh model đoán bừa ngôn ngữ/framework rồi đưa code sai hoàn toàn, tiết kiệm vòng lặp qua lại không cần thiết.


### Câu 4.2 — Hạn chế & cải thiện
**Trợ lý của bạn hiện có hạn chế lớn nhất là gì (ví dụ: history chỉ 3 lượt,
không có bộ nhớ dài hạn, không kiểm duyệt nội dung...)? Đề xuất một cải
thiện cụ thể và mô tả ngắn cách triển khai:**
> Hạn chế lớn nhất là do history ngắn nên không thể chuyên sâu vào câu trả lời -> có thể cải thiện bằng cách tăng thêm capacity của memory và dùng call back iteration.

---

## Danh Sách Kiểm Tra Nộp Bài

- [ ] `python grade.py` — xem điểm tự động, mục tiêu ≥ 75/100
- [ ] Cả 4 checkpoint pytest đều pass
- [ ] Tất cả 9 câu trong file này đã được trả lời
- [ ] Đã copy bài làm vào folder `solution/`, push lên fork và dán link trên trang bài Lab ở VLearn trước 23:59 ngày 11/09/2026
