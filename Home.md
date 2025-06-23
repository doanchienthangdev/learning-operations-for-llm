# Learning with AI API

## Nhóm 1: Tóm tắt và Cô đọng Kiến thức

Nhóm này tập trung vào việc rút gọn thông tin, chắt lọc những ý quan trọng nhất từ một nguồn nội dung lớn.

### `zip()`: Tóm tắt kiến thức quan trọng nhất theo số câu cho trước

```python
zip(n_sentences=5, context=answer, topic=””)
```

**Giải thích:** Hàm `zip()` hoạt động như một "máy nén kiến thức". Chức năng chính của nó là đọc một khối lượng lớn văn bản từ một nguồn cho trước và chắt lọc ra những ý tưởng cốt lõi, quan trọng nhất, sau đó trình bày chúng lại dưới dạng một bản tóm tắt cực kỳ cô đọng trong đúng `n` câu. Hàm này đặc biệt hữu ích khi bạn muốn nắm bắt nhanh ý chính của một tài liệu dài mà không có thời gian đọc toàn bộ, hoặc khi bạn cần ôn lại những điểm mấu chốt của một bài học đã qua. Nó buộc AI phải xác định đâu là thông tin không thể thiếu, giúp bạn tập trung vào phần tinh túy nhất của kiến thức.

Chức năng của nó là tóm tắt những kiến thức quan trọng nhất có trong một nguồn thông tin (`context`) bằng một số lượng câu (`sentences`) cụ thể về một chủ đề (`topic`) nhất định. Điều này giúp người dùng nhanh chóng chắt lọc những ý chính từ một nội dung lớn.

- **Tham số:**
    - `sentences`: Xác định số câu trong bản tóm tắt. Nếu không được chỉ định, giá trị mặc định là 5.
    - `context`: Là nguồn thông tin để tóm tắt, có thể là câu trả lời trước đó (`answer`), file đính kèm (`files`), hoặc không có (`""`). Giá trị mặc định là `answer`. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `topic`: Chủ đề cụ thể mà bản tóm tắt cần tập trung vào. Nếu để trống, giá trị mặc định là `""`.
- **Ví dụ:**
    - `zip(10, files)`: Tóm tắt những kiến thức quan trọng nhất trong file đính kèm bằng 10 câu.
    - `zip()`: Tóm tắt những kiến thức quan trọng nhất trong phần trả lời bằng 5 câu.
    - `zip(15, files, “Python List”)`: Tóm tắt những kiến thức quan trọng nhất trong files đính kèm bằng 15 câu về chủ đề “Python List”.

### `core_ideas()`: Những ý tưởng cốt lõi

```python
core_ideas(context=answer, quantity=3)
```

Hàm `core_ideas()` tập trung vào việc chắt lọc và trình bày các **luận điểm, thông điệp, hoặc ý tưởng cốt lõi** mà tác giả muốn truyền tải. Nó trả lời cho câu hỏi: "Sau khi đọc xong văn bản này, đâu là những tuyên bố hoặc kết luận chính mà tôi cần phải nhớ?".

Hàm này khác với `zip()` (tóm tắt toàn bộ nội dung) và `core_concepts()` (liệt kê thuật ngữ). `core_ideas()` chỉ rút ra những câu mang tính khẳng định, những lập luận trung tâm, giúp bạn nắm bắt nhanh chóng tư tưởng chính của tài liệu.

- **Tham số:**
    - `context`: (Bắt buộc, mặc định là `answer`) Nguồn văn bản để chắt lọc ý tưởng. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `quantity`: (Số nguyên, mặc định là 3) Số lượng ý tưởng cốt lõi quan trọng nhất mà bạn muốn AI liệt kê.
- **Ví dụ:**
    - `core_ideas(context=files)`: Đọc file đính kèm và rút ra 3 luận điểm chính mà tác giả đưa ra.
    - `core_ideas(context=answer, quantity=5)`: Liệt kê 5 thông điệp cốt lõi từ câu trả lời dài của AI.

### `core_concepts()`: Các khái niệm cốt lõi

```python
core_concepts(context=answer, quantity=5, explanation_style="brief", topic="")
```

**Giải thích:** Hàm `core_concepts()` hoạt động như một "máy quét khái niệm". Khi bạn đối mặt với một tài liệu hoặc một chủ đề mới và dày đặc thông tin, hàm này sẽ tự động phân tích toàn bộ văn bản để xác định và rút ra những khái niệm, thuật ngữ, hoặc ý tưởng nền tảng quan trọng nhất. Sau đó, nó sẽ liệt kê và diễn giải ngắn gọn từng khái niệm đó.

Công cụ này cực kỳ hữu ích để xây dựng một bộ từ vựng cơ bản trước khi đi sâu vào nghiên cứu. Nó giúp bạn nhanh chóng nắm bắt được đâu là những "trụ cột" kiến thức của chủ đề, từ đó định hướng việc học và đọc hiểu một cách hiệu quả hơn.

- **Tham số:**
    - `context`: (Bắt buộc, mặc định là `answer`) Nguồn văn bản để AI phân tích và rút trích khái niệm. Đây là tham số quan trọng nhất của hàm. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
        - `answer`: Sử dụng chính câu trả lời trước đó của AI.
        - `files`: Sử dụng nội dung từ file bạn đính kèm.
    - `quantity`: (Số nguyên, mặc định là 5) Số lượng khái niệm cốt lõi quan trọng nhất mà bạn muốn AI liệt kê.
    - `explanation_style`: (Văn bản, mặc định là `brief`) Quy định độ dài của phần diễn giải cho mỗi khái niệm.
        - `brief`: Diễn giải ngắn gọn, súc tích trong một câu.
        - `detailed`: Diễn giải chi tiết hơn trong một đoạn văn ngắn.
        - `feynman`: Diễn giải dùng kỹ thuật Feynman
    - `topic`: (Văn bản, mặc định là `""`) Nếu `context` quá rộng, tham số này giúp AI tập trung tìm kiếm các khái niệm cốt lõi xoay quanh một chủ đề phụ cụ thể.
- **Ví dụ:**
    - `core_concepts(context=files)`: Đọc file đính kèm (ví dụ: một bài báo khoa học) và liệt kê 5 khái niệm quan trọng nhất cùng với lời giải thích ngắn gọn cho mỗi khái niệm.
    - `core_concepts(context=answer, quantity=8, explanation_style="detailed")`: Dựa vào câu trả lời trước của AI, liệt kê 8 khái niệm cốt lõi và giải thích chi tiết hơn về từng khái niệm.
    - `core_concepts(context=files, topic="phần phương pháp luận")`: Chỉ quét phần phương pháp luận trong file và rút ra các khái niệm chính được sử dụng trong phần đó.

### `tutor_mode()`: Đóng vai gia sư, dạy kiến thức

```python
tutor_mode(context, topic="", start_level="Understand", questions_per_level=3)
```

**Giải thích:** Hàm `tutor_mode()` là một trong những chức năng học tập tương tác và mạnh mẽ nhất, biến AI thành một gia sư 1-kèm-1. Khi được kích hoạt, nó sẽ bắt đầu một phiên dạy và học có cấu trúc về nội dung trong `context`, dựa trên phương pháp sư phạm nổi tiếng **Thang nhận thức Bloom (Bloom's Taxonomy)**.

AI sẽ tuần tự đặt các câu hỏi từ cấp độ tư duy thấp đến cao (Ghi nhớ -> Hiểu -> Áp dụng -> Phân tích -> Đánh giá -> Sáng tạo). Dạng câu hỏi (trắc nghiệm, tự luận, lập trình,...) sẽ được tự động điều chỉnh cho phù hợp với nội dung và cấp độ Bloom. Sau mỗi câu trả lời của bạn, AI sẽ đưa ra nhận xét, giải thích đáp án đúng, và hỏi bạn có muốn tiếp tục hay không. Đây là một chu trình học tập khép kín giúp củng cố kiến thức một cách vững chắc và hiệu quả.

- **Tham số:**
    - `context`: (Bắt buộc) Nguồn kiến thức mà buổi học sẽ xoay quanh. Tham số này **không có giá trị mặc định** và bắt buộc phải được cung cấp. Có thể là `files` hoặc `answer`. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `topic`: (Văn bản, mặc định là `""`) Cho phép bạn giới hạn phạm vi của buổi học vào một chủ đề cụ thể trong `context`.
    - `start_level`: (Văn bản, mặc định là `Understand`) Mức độ bắt đầu trên thang Bloom. Bạn có thể bỏ qua các cấp độ cơ bản nếu muốn. Các cấp độ bao gồm:
        - `Understand` (Hiểu)
        - `Remember` (Ghi nhớ)
        - `Apply` (Áp dụng)
        - `Analyze` (Phân tích)
        - `Evaluate` (Đánh giá)
        - `Create` (Sáng tạo)
    - `questions_per_level`: (Số nguyên, mặc định là 3) Số lượng câu hỏi AI sẽ hỏi ở mỗi cấp độ Bloom trước khi đề nghị chuyển lên cấp độ tiếp theo.

**Mô tả Luồng hoạt động**

`tutor_mode()` hoạt động theo một luồng tương tác theo lượt:

- **Bước 1: Khởi tạo Chế độ**
    - Bạn gọi hàm để bắt đầu. Ví dụ: `tutor_mode(context=files, topic="Quang hợp")`.
- **Bước 2: Đặt câu hỏi theo cấp độ Bloom**
    - AI sẽ bắt đầu ở cấp độ `start_level` (mặc định là "Ghi nhớ").
    - AI sẽ thông báo cấp độ hiện tại và đặt câu hỏi đầu tiên. Ví dụ:
        - *"Chào bạn, chúng ta hãy bắt đầu buổi học về 'Quang hợp'. Bắt đầu với cấp độ **Ghi nhớ** nhé. Câu hỏi 1: Đâu là hai sản phẩm chính được tạo ra từ quá trình quang hợp?"*
- **Bước 3: Bạn trả lời**
    - Bạn nhập câu trả lời của mình.
- **Bước 4: Nhận xét và Giải thích**
    - AI sẽ phân tích câu trả lời của bạn, đưa ra nhận xét (ví dụ: "Chính xác!" hoặc "Gần đúng rồi, tuy nhiên...").
    - Sau đó, AI sẽ cung cấp lời giải thích chi tiết cho đáp án đúng để củng cố kiến thức cho bạn.
- **Bước 5: Hỏi để Tiếp tục**
    - AI sẽ hỏi bạn có muốn tiếp tục không. Ví dụ:
        - *"Bạn có muốn tiếp tục với một câu hỏi khác ở cấp độ **Ghi nhớ** không? (Gõ 'OK' hoặc 'đồng ý' để tiếp tục)"*
- **Bước 6: Lặp lại hoặc Kết thúc**
    - Nếu bạn trả lời "OK" hoặc "đồng ý", AI sẽ quay lại Bước 2 và đặt câu hỏi tiếp theo ở cấp độ hiện tại. Khi đã đủ số câu hỏi (`questions_per_level`), AI sẽ đề nghị chuyển lên cấp độ Bloom tiếp theo.
    - Nếu bạn trả lời khác, hoặc không trả lời, chế độ gia sư sẽ kết thúc với một lời chào.

**Ví dụ cách dùng**

- `tutor_mode(context=files, topic="Lịch sử Việt Nam giai đoạn 1945-1975")`
    - Bắt đầu một buổi học đầy đủ về lịch sử Việt Nam từ một file tài liệu bạn tải lên, đi từ cấp độ Ghi nhớ các sự kiện cho đến Sáng tạo (ví dụ: yêu cầu viết một bài luận ngắn).
- `tutor_mode(context=answer, start_level="Apply")`
    - Dựa trên câu trả lời dài trước đó của AI, hãy bỏ qua các câu hỏi Ghi nhớ/Hiểu và bắt đầu ngay với các câu hỏi yêu cầu Áp dụng kiến thức.
- `tutor_mode(context=files, topic="Python List Comprehension", questions_per_level=2)`
    - Bắt đầu một buổi học về List Comprehension trong Python, và chỉ hỏi 2 câu ở mỗi cấp độ Bloom trước khi chuyển lên cấp độ cao hơn.

## Nhóm 2: Diễn giải và Đơn giản hóa Kiến thức, khái niệm

### `feynman()`: Giải thích một chủ đề bằng ngôn ngữ đơn giản nhất có thể.

```python
feynman(topic, context=answer, target_audience="học sinh lớp 5")
```

**Giải thích:** Sử dụng Kỹ thuật Feynman, một phương pháp học tập nổi tiếng, để giải thích một chủ đề phức tạp bằng ngôn ngữ đơn giản và dễ hiểu nhất có thể, như thể đang giải thích cho một đối tượng cụ thể không có chuyên môn.

- **Tham số:**
    - `topic`: Chủ đề hoặc thuật ngữ cần được giải thích.
    - `context`: Nguồn thông tin để giải thích (câu trả lời của AI, file đính kèm, hoặc không có). Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `target_audience`: Đối tượng người nghe mà AI cần hướng tới (ví dụ: "người mới bắt đầu", "chuyên gia ngành khác", "học sinh lớp 5", "người không rành công nghệ").
- **Ví dụ:**
    - `feynman("API là gì?", files, "người bà của tôi")`: Yêu cầu AI giải thích khái niệm API từ nội dung trong file đính kèm bằng ngôn ngữ cực kỳ đơn giản để một người lớn tuổi, không dùng công nghệ có thể hiểu được.
    - `feynman("Blockchain")`: Giải thích khái niệm Blockchain như cho học sinh lớp 5.

### `analogy()`: Tạo các phép so sánh, ẩn dụ để liên hệ kiến thức mới với kiến thức cũ

```python
analogy(topic, context=answer, quantity=3)
```

**Giải thích:** Tạo ra các phép so sánh, ẩn dụ hoặc ví dụ liên tưởng để kết nối một khái niệm mới, trừu tượng với một khái niệm quen thuộc, giúp việc hiểu và ghi nhớ trở nên dễ dàng hơn.

- **Tham số:**
    - `topic`: Chủ đề cần tạo ví dụ so sánh.
    - `context`: Nguồn thông tin. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `quantity`: Số lượng ví dụ so sánh cần tạo.
- **Ví dụ:**
    - `analogy("Machine Learning", "", 5)`: Tạo 5 phép so sánh/ẩn dụ để giải thích Machine Learning là gì.

### `persona()`: Giải thích một chủ đề dưới góc nhìn của một nhân vật cụ thể

```python
persona(persona, topic, context=answer)
```

**Giải thích:** Yêu cầu AI đóng một vai trò, nhân vật cụ thể để giải thích một chủ đề. Phương pháp này giúp đưa ra những góc nhìn độc đáo, chuyên sâu hoặc thú vị về cùng một vấn đề.

- **Tham số:**
    - `persona`: Vai trò AI cần đóng (ví dụ: "một nhà sử học", "một lập trình viên kinh nghiệm", "Sherlock Holmes", "Steve Jobs").
    - `topic`: Chủ đề cần giải thích.
    - `context`: Nguồn thông tin. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
- **Ví dụ:**
    - `persona("Sherlock Holmes", "Phân tích dữ liệu trong file", files)`: Yêu cầu AI đóng vai Sherlock Holmes để phân tích và suy luận về dữ liệu trong file đính kèm.

### `story()`: Lồng ghép kiến thức vào một câu chuyện để tăng sự hấp dẫn và dễ nhớ

```python
story(topic, context=answer, genre="khoa học viễn tưởng")
```

**Giải thích:** Lồng ghép một khái niệm hoặc một bài học vào một câu chuyện. Việc kể chuyện giúp thông tin trở nên hấp dẫn, dễ nhớ và có cảm xúc hơn.

- **Tham số:**
    - `topic`: Chủ đề cần lồng vào câu chuyện.
    - `context`: Nguồn thông tin. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt
    - `genre`: Thể loại truyện (ví dụ: "trinh thám", "cổ tích", "đời thường", "lịch sử").
- **Ví dụ:**
    - `story("Sự hình thành của một thói quen tốt", "", "đời thường")`: Kể một câu chuyện đời thường để minh họa cho quá trình hình thành một thói quen tốt.

### `mental_model()`: Mô tả mô hình tư duy cốt lõi đằng sau một khái niệm

```python
mental_model(topic, context=answer)
```

**Giải thích:** Mô tả (các) mô hình tư duy cốt lõi đứng sau một khái niệm hoặc một hệ thống. Hiểu được mô hình tư duy giúp người học có một khuôn khổ vững chắc để suy luận và áp dụng kiến thức.

- **Tham số:**
    - `topic`: Khái niệm, hệ thống cần tìm mô hình tư duy.
    - `context`: Nguồn thông tin. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
- **Ví dụ:**
    - `mental_model("Git version control")`: Mô tả mô hình tư duy về các "snapshot", "branch", "commit" giúp hiểu sâu cách Git hoạt động.

### `dejargonize()`: "Dịch" các thuật ngữ chuyên ngành sang ngôn ngữ đời thường

```python
dejargonize(context=answer, target_audience="a high school student")
```

**Giải thích:** "Dịch" một đoạn văn bản chứa nhiều thuật ngữ chuyên ngành, phức tạp thành ngôn ngữ đơn giản, dễ hiểu cho một đối tượng cụ thể.

- **Tham số:**
    - `context`: Đoạn văn bản cần được đơn giản hóa (trong `answer` hoặc `files`). Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `target_audience`: Đối tượng người đọc mà bản dịch hướng tới.
- **Ví dụ:**
    - `dejargonize(context=files, target_audience="an investor with no tech background")`: Yêu cầu AI đọc một tài liệu kỹ thuật trong file và giải thích nó bằng ngôn ngữ kinh doanh cho nhà đầu tư.

### `explain_by_contrast()`: Giải thích một khái niệm bằng cách đối chiếu nó với một khái niệm khác

```python
explain_by_contrast(topic, contrasting_topic, context="")
```

**Giải thích:** Giải thích một khái niệm không chỉ bằng cách định nghĩa nó là gì, mà còn bằng cách so sánh và làm rõ nó *không phải là gì* thông qua một khái niệm đối lập hoặc thường bị nhầm lẫn.

- **Tham số:**
    - `topic`: Khái niệm cần giải thích.
    - `contrasting_topic`: Khái niệm dùng để đối chiếu.
    - `context`: Nguồn thông tin. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
- **Ví dụ:**
    - `explain_by_contrast(topic="Agile methodology", contrasting_topic="Waterfall methodology")`: Giải thích Agile bằng cách liên tục đối chiếu nó với mô hình Waterfall truyền thống.

## Nhóm 3: Hệ thống hóa và Lập kế hoạch Học tập

Nhóm này giúp người học có cái nhìn tổng quan, cấu trúc hóa thông tin và xây dựng một lộ trình học tập rõ ràng.

### `mindmap()`: Tạo sơ đồ tư duy để hệ thống hóa thông tin

```python
Mindmap(topic, context=answer, format="markdown")
```

**Giải thích:** Hệ thống hóa và trình bày thông tin về một chủ đề dưới dạng một sơ đồ tư duy. Giúp người học có cái nhìn tổng quan, thấy được sự liên kết giữa các ý chính và ý phụ.

- **Tham số:**
    - `topic`: Chủ đề chính của sơ đồ tư duy.
    - `context`: Nguồn thông tin để tạo sơ đồ. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `format`: Định dạng đầu ra của sơ đồ (ví dụ: `markdown list` - danh sách markdown, `text tree` - cây thư mục dạng văn bản, `json` - cấu trúc json, `flow_chart` - Trình bày dưới dạng mã Mermaid để có thể vẽ thành sơ đồ luồng).
- **Ví dụ:**
    - `mindmap("Các loại hình Marketing Online", files, "text tree")`: Tạo sơ đồ tư duy dạng cây về các loại hình Marketing Online dựa trên nội dung file.

### `idea_development()`: Trực quan hoá quá trình phát triển ý tưởng

```python
idea_development(context=answer, format="text_tree", root_idea="")
```

**Giải thích:** Hàm `idea_development()` được dùng để trực quan hóa luồng phát triển của các lập luận hoặc ý tưởng trong một văn bản. Thay vì chỉ liệt kê các ý chính, hàm này sẽ tạo ra một "cây phát triển", cho thấy ý tưởng này được xây dựng dựa trên ý tưởng kia như thế nào, lập luận chính được hỗ trợ bởi các luận điểm phụ ra sao.

Công cụ này rất hữu ích để phân tích cấu trúc logic của một bài viết, một bài tranh luận, hoặc một chương sách. Nó giúp bạn hiểu được quá trình tư duy và cách tác giả dẫn dắt người đọc từ tiền đề đến kết luận.

- **Tham số:**
    - `context`: (Bắt buộc, mặc định là `answer`) Nguồn văn bản để phân tích luồng ý tưởng. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `format`: (Văn bản, mặc định là `text_tree`) Định dạng của cây phát triển.
        - `text_tree`: Trình bày dưới dạng cây thư mục bằng văn bản.
        - `flow_chart`: Trình bày dưới dạng mã Mermaid để có thể vẽ thành sơ đồ luồng.
        - `json`: Trình bày dưới dạng json
    - `root_idea`: (Văn bản, mặc định là `""`) Cho phép bạn chỉ định một ý tưởng gốc để AI bắt đầu phân tích sự phát triển từ đó. Nếu để trống, AI sẽ tự xác định luận điểm chính của văn bản.
- **Ví dụ:**
    - `idea_development(context=files)`: Phân tích file đính kèm và trình bày cấu trúc phát triển các ý tưởng chính dưới dạng cây thư mục.
    - `idea_development(context=answer, format="flow_chart")`: Vẽ sơ đồ luồng phát triển các lập luận trong câu trả lời trước đó của AI.

### `decompose()`: Phân rã một vấn đề lớn thành các bước nhỏ hơn

```python
decompose(problem, context=answer)
```

**Giải thích:** Phân rã một vấn đề lớn, một quy trình phức tạp hoặc một mục tiêu thành các bước nhỏ hơn, cụ thể và dễ quản lý hơn. Đây là bước đầu tiên và quan trọng nhất trong việc giải quyết vấn đề.

- **Tham số:**
    - `problem`: Vấn đề hoặc quy trình phức tạp cần chia nhỏ.
    - `context`: Nguồn thông tin để thực hiện phân rã. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
- **Ví dụ:**
    - `decompose("Làm thế nào để xây dựng một kênh YouTube thành công?")`: Chia nhỏ mục tiêu "xây dựng kênh YouTube thành công" thành các bước hành động cụ thể.

### `logical_structure()`: Phân tích cấu trúc logic và mạch lạc lập luận của một văn bản

```python
logical_structure(context=answer, format="outline", detail_level="high_level")
```

**Giải thích:** Hàm `logical_structure()` hoạt động như một công cụ "X-quang" để phân tích bộ khung và mạch lạc lập luận của một văn bản. Thay vì tập trung vào "nội dung là gì", hàm này tập trung vào "nội dung được tổ chức như thế nào". Nó sẽ xác định và mô tả cấu trúc logic mà tác giả đã sử dụng, ví dụ như cấu trúc Vấn đề - Giải pháp, So sánh - Đối chiếu, Luận điểm - Luận cứ - Kết luận, hay một chuỗi nhân quả.

Việc hiểu được cấu trúc logic này giúp bạn đọc hiểu một cách chủ động hơn, dễ dàng xác định được đâu là luận điểm chính, đâu là luận cứ hỗ trợ, và đánh giá được sự chặt chẽ, thuyết phục của toàn bộ lập luận.

- **Tham số:**
    - `context`: (Bắt buộc, mặc định là `files`) Nguồn văn bản cần được phân tích cấu trúc logic. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `format`: (Văn bản, mặc định là `outline`) Định dạng của kết quả phân tích.
        - `outline`: Trình bày cấu trúc dưới dạng một dàn ý chi tiết (sử dụng gạch đầu dòng hoặc số thứ tự).
        - `summary`: Viết một đoạn văn mô tả mạch lạc và luồng chảy của lập luận.
        - `framework_id`: Chỉ gọi tên loại cấu trúc logic được sử dụng (ví dụ: "Cấu trúc So sánh - Đối chiếu", "Cấu trúc Nguyên nhân - Kết quả").
    - `detail_level`: (Văn bản, mặc định là `high_level`) Mức độ chi tiết của dàn ý (chỉ áp dụng cho `format="outline"`).
        - `high_level`: Chỉ bao gồm các phần chính và các luận điểm chính.
        - `detailed`: Bao gồm cả các luận điểm phụ, ví dụ, và các chi tiết hỗ trợ.
- **Ví dụ:**
    - `logical_structure(context=files)`: Phân tích file đính kèm (ví dụ: một bài xã luận) và trình bày dàn ý cấp cao về cấu trúc lập luận của nó.
    - `logical_structure(context=answer, format="framework_id")`: Sau khi nhận được một câu trả lời dài từ AI, hãy yêu cầu nó cho biết cấu trúc logic mà nó đã sử dụng để trả lời.
    - `logical_structure(context=files, detail_level="detailed")`: Tạo một dàn ý cực kỳ chi tiết về cấu trúc logic của tài liệu trong file, giúp cho việc phân tích sâu.

### `learning_path()`: Tạo lộ trình học tập chi tiết cho một chủ đề

```python
learning_path(topic, context=files, current_level="người mới bắt đầu", goal_level="thành thạo", resources="miễn phí")
```

**Giải thích:** Tạo ra một lộ trình học tập chi tiết và có cấu trúc cho một chủ đề mới. Lộ trình này sẽ bao gồm các bước, các chủ đề con cần học và đề xuất tài nguyên phù hợp.

- **Tham số:**
    - `topic`: Chủ đề cần xây dựng lộ trình học.
    - `context`: Bối cảnh làm nguồn tài liệu tham khảo. Chương trình học sẽ bám sát tài liệu này. Nếu để context = “” thì tự chọn tài liệu. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `current_level`: Trình độ hiện tại của người học.
    - `goal_level`: Mục tiêu trình độ muốn đạt được.
    - `resources`: Loại tài nguyên mong muốn (ví dụ: "miễn phí", "có phí", "sách", "dự án thực tế").
- **Ví dụ:**
    - `learning_path("Học guitar", context=files, "chưa biết gì", "chơi được đệm hát cơ bản", "miễn phí")`: Tạo lộ trình tự học guitar đệm hát từ đầu với các tài nguyên miễn phí trên mạng bám theo nội dung của files đính kèm.

### `concept_map()`: Tạo bản đồ khái niệm, tập trung vào mối quan hệ giữa các ý tưởng

```python
concept_map(topic, context=answer, format="mermaid")
```

**Giải thích:** Tạo ra một bản đồ khái niệm, tập trung vào việc chỉ rõ mối quan hệ (dưới dạng các động từ) giữa các khái niệm (danh từ). Điều này khác với sơ đồ tư duy (mind map) vốn chỉ tập trung vào phân cấp.

- **Tham số:**
    - `topic`: Chủ đề trung tâm.
    - `context`: Nguồn thông tin. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `format`: Định dạng đầu ra ("list" - danh sách, "mermaid" - mã để vẽ biểu đồ).
- **Ví dụ:**
    - `concept_map(topic="Machine Learning", format="list")`: Có thể tạo ra kết quả như: "[Machine Learning] --(is a field of)--> [Artificial Intelligence]", "[Machine Learning] --(uses)--> [Algorithms]", "[Algorithms] --(are trained with)--> [Data]".

### `design_syllabus()`: Thiết kế một đề cương chi tiết cho cả một môn học/khóa học

```python
design_syllabus(course_title, duration="12 weeks", target_audience, learning_objectives=5)
```

- **Giải thích:** Tạo ra một đề cương chi tiết cho một môn học hoặc khóa học, bao gồm mục tiêu học tập, lịch trình theo tuần, các chủ đề chính, bài đọc gợi ý và hình thức đánh giá.
- **Tham số:**
    - `course_title`: Tên môn học.
    - `duration`: Thời lượng khóa học.
    - `target_audience`: Đối tượng học viên.
    - `learning_objectives`: Số lượng mục tiêu học tập chính cần xác định.
- **Ví dụ:**
    - `design_syllabus(course_title="Introduction to Digital Marketing", duration="8 weeks", target_audience="Small business owners")`.

## Nhóm 4: Kiểm tra và Củng cố Chủ động

Nhóm này thúc đẩy việc chủ động truy xuất kiến thức (active recall) và tự kiểm tra, những phương pháp đã được chứng minh là cực kỳ hiệu quả để ghi nhớ lâu dài.

### `questions()`: Tạo các câu hỏi trắc nghiệm hoặc tự luận

```python
questions(quantity=1, type=multiple_choice, difficulty=normal, context=answer, topic=””)
```

**Giải thích:** Hàm `questions()` được dùng để tạo ra một số lượng (`quantity`) câu hỏi theo một dạng thức (`type`) và độ khó (`difficulty`) nhất định về một chủ đề (`topic`) dựa trên nguồn thông tin (`context`) được cung cấp. Các câu hỏi sẽ được đưa lần lượt, người dùng trả lời, sau đó nhận xét đáp án, đưa ra câu trả lời đúng, nêu bài học rút ra và chấm điểm. Người dùng được hỏi có tiếp tục không. Nếu người dùng gõ OK hoặc đồng ý thì tiếp tục cho đến khi hết quantity câu. Nếu không thì dừng quá trình hỏi.

- **Tham số:**
    - `quantity`: Số lượng câu hỏi cần tạo. Mặc định là 1.
    - `type`: Dạng câu hỏi. Các dạng có thể bao gồm `multiple_choice`, `multi_select`, `write_correct_answer`, và `programming_with_test_cases`. Mặc định là `multiple_choice`.
    - `difficulty`: Độ khó của câu hỏi, bao gồm các mức: `easy`, `normal`, `hard`, `very hard`, `challenge`. Mặc định là `normal`.
    - `context`: Nguồn thông tin để tạo câu hỏi, có thể là `answer`, `files`, hoặc `""`. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `topic`: Chủ đề cụ thể của câu hỏi. Mặc định là `""`

### `flashcards()`: Tạo các thẻ học (flashcard) ảo với mặt trước và mặt sau

```python
 Flashcards(topic, context=answer, quantity=10)
```

**Giải thích:** Tạo ra các thẻ học (flashcard) ảo với định dạng câu hỏi/thuật ngữ ở mặt trước và câu trả lời/định nghĩa ở mặt sau. Đây là công cụ tuyệt vời cho việc ôn tập và kiểm tra kiến thức theo phương pháp chủ động truy xuất (active recall).

- **Tham số:**
    - `topic`: Chủ đề của các thẻ học.
    - `context`: Nguồn thông tin để tạo thẻ. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `quantity`: Số lượng thẻ cần tạo.
- **Ví dụ:**
    - `Flashcards("Từ vựng IELTS band 8.0", files, 20)`: Tạo 20 flashcard (từ/định nghĩa) từ danh sách từ vựng trong file đính kèm.

### `challenge_question()`: Đặt ra các câu hỏi thách đố, hóc búa để kiểm tra giới hạn kiến thức

```python
challenge_questions(topic, quantity=1 context=answer, level="expert", type="paradox")
```

**Giải thích:** Đặt ra những câu hỏi thách đố, hóc búa để kiểm tra giới hạn kiến thức. Bên cạnh câu hỏi thông thường, nó có thể tập trung vào các tình huống ngoại lệ (edge cases), nghịch lý (paradoxes), hoặc các câu hỏi "what-if" để thúc đẩy tư duy phản biện.

- **Tham số:**
    - `topic`: Chủ đề để đặt câu hỏi.
    - `quantity`: số lượng câu hỏi
    - `context`: Nguồn thông tin. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `level`: Độ khó của câu hỏi ("easy", "medium", "hard", "expert").
    - `type`: Loại câu hỏi (”” - câu hỏi chung chung, "`edge_case`" - tình huống ngoại lệ, "`paradox`" - nghịch lý, "`what_if`" - giả định, "`synthesis`" - tổng hợp kiến thức, `extreme-situation` - tình huống cực biên).
- **Ví dụ:**
    - `challenge_question(topic="Time Travel", quantity=2, type="paradox")`: Đặt ra 2 câu hỏi liên quan đến nghịch lý ông nội (grandfather paradox) trong du hành thời gian.

### `find_the_flaw()`: Yêu cầu người học tìm ra lỗi sai trong một nội dung cho trước

```python
find_the_flaw(context, flaw_type="logic")
```

**Giải thích:** AI sẽ tạo ra một đoạn văn bản, một đoạn code, hoặc một lập luận có chứa các lỗi sai tiềm ẩn. Nhiệm vụ của bạn là tìm và chỉ ra các lỗi sai đó.

- **Tham số:**
    - `context`: Chủ đề để AI tạo ra nội dung có lỗi. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `flaw_type`: Loại lỗi cần tạo ("logic" - lỗi logic, "factual" - sai sự thật, "syntax" - sai cú pháp, "security" - lỗ hổng bảo mật).
- **Ví dụ:**
    - `find_the_flaw(context="A Python function to calculate the average of a list", flaw_type="logic")`: AI có thể tạo ra một hàm tính trung bình nhưng lại chia sai cho số phần tử hoặc không xử lý trường hợp list rỗng.

## Nhóm 5: Tư duy Phản biện và Phân tích Sâu

Nhóm này tập trung vào việc đào sâu suy nghĩ, thử thách các giả định và phân tích vấn đề từ nhiều góc độ khác nhau.

### `deep_explain()`: Giải thích sâu về 1 chủ đề

```python
deep_explain(topic, aspects=["all"], level="intermediate", context=answer)
```

**Giải thích:** Hàm `deep_explain()` được tạo ra để vượt qua một lời giải thích bề mặt, cung cấp một cái nhìn sâu sắc, đa chiều và có cấu trúc về một chủ đề. Thay vì chỉ định nghĩa "nó là gì", hàm này sẽ phân tích chủ đề thành nhiều khía cạnh cốt lõi như lịch sử hình thành, cơ chế hoạt động, ứng dụng, ưu nhược điểm, và cả những hiểu lầm phổ biến.

Đây là công cụ lý tưởng khi bạn muốn thực sự làm chủ một kiến thức, hiểu rõ gốc rễ và các mối liên hệ của nó. Bằng cách cho phép người dùng lựa chọn các khía cạnh (`aspects`) muốn tìm hiểu, hàm này mang lại một trải nghiệm học tập tùy chỉnh và hiệu quả, giúp xây dựng một nền tảng kiến thức vững chắc và toàn diện.

- **Tham số:**
    - `topic`: (Bắt buộc) Chủ đề, khái niệm, hoặc thuật ngữ bạn muốn được giải thích sâu.
    - `aspects`: (Danh sách, mặc định là `["all"]`) Tham số quan trọng nhất cho phép bạn chọn các khía cạnh cụ thể của chủ đề để đào sâu.
        - `all`: Giải thích tất cả các khía cạnh có thể.
        - `definition`: Định nghĩa cốt lõi và chính xác.
        - `history`: Lịch sử hình thành và quá trình phát triển.
        - `mechanism`: Cơ chế hoạt động, giải thích cách nó hoạt động "bên trong".
        - `types`: Các loại, các dạng hoặc các thành phần chính.
        - `applications`: Các ứng dụng trong thực tế và ví dụ.
        - `pros_cons`: Phân tích ưu điểm và nhược điểm một cách cân bằng.
        - `misconceptions`: Làm rõ những hiểu lầm phổ biến liên quan đến chủ đề.
        - `future`: Các xu hướng và triển vọng phát triển trong tương lai.
    - `level`: (Văn bản, mặc định là `intermediate`) Điều chỉnh mức độ chuyên sâu của lời giải thích cho phù hợp với trình độ của bạn (`beginner`, `intermediate`, `expert`).
    - `context`: (Văn bản, mặc định là `answer`) Nguồn thông tin để AI dựa vào đó giải thích (ví dụ: một bài báo khoa học trong `files`). Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
- **Ví dụ:**
    - `deep_explain("Trí tuệ nhân tạo")`: Yêu cầu một bài giải thích toàn diện về AI, bao gồm tất cả các khía cạnh từ lịch sử, các loại AI, ứng dụng, cho đến ưu nhược điểm và tương lai.
    - `deep_explain("API", aspects=["mechanism", "applications"])`: Chỉ tập trung giải thích sâu về cách API hoạt động và các ứng dụng thực tế của nó.
    - `deep_explain("Thuyết tương đối rộng", level="expert", aspects=["mechanism", "misconceptions"])`: Yêu cầu giải thích cơ chế của Thuyết tương đối rộng ở mức độ chuyên gia và làm rõ những hiểu lầm thường gặp.
    - `deep_explain("chiến lược kinh doanh được đề xuất", context=files, aspects=["pros_cons"])`: Phân tích sâu ưu và nhược điểm của chiến lược kinh doanh được mô tả trong file đính kèm.

### `socratic_dialogue()`: Bắt đầu chuỗi hội thoại truy vấn để người học tự tìm ra câu trả lời

```python
socratic_dialogue(topic, user_statement, persona="Socrates")
```

**Giải thích:** Bắt đầu một chuỗi hội thoại tương tác theo phương pháp Socrates. AI sẽ không đưa ra câu trả lời trực tiếp mà liên tục đặt câu hỏi sâu sắc dựa trên câu trả lời của bạn (`user_statement`), nhằm thử thách các giả định và dẫn dắt bạn tự khám phá bản chất vấn đề. Đây là một chế độ tương tác theo lượt.

- **Tham số:**
    - `topic`: Chủ đề chính của cuộc hội thoại.
    - `user_statement`: Quan điểm, niềm tin ban đầu của bạn về chủ đề đó.
    - `persona`: Vai trò của AI (mặc định là "Socrates", có thể là "một giáo viên khó tính", "một đứa trẻ tò mò"...).
- **Ví dụ:**
    - `socratic_dialogue(topic="Nghệ thuật", user_statement="Nghệ thuật là cái đẹp.")`: AI sẽ bắt đầu bằng một câu hỏi như, "Vậy một bức tranh gây khó chịu nhưng lại khiến người xem suy ngẫm sâu sắc thì có được coi là nghệ thuật không?" và tiếp tục dựa trên câu trả lời của bạn.

### `first_principles()`: Phân tích một chủ đề về những nguyên tắc cơ bản nhất

```python
first_principles(topic, context=answer)
```

**Giải thích:** Phân tích một chủ đề bằng cách "tư duy từ nguyên tắc đầu tiên", tức là phá vỡ nó thành những sự thật hoặc nguyên lý cơ bản nhất, không thể giản lược hơn được nữa, và sau đó xây dựng lại sự hiểu biết từ đó.

- **Tham số:**
    - `topic`: Chủ đề cần phân tích.
    - `context`: Nguồn thông tin. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
- **Ví dụ:**
    - `FirstPrinciples("Giao tiếp hiệu quả")`: Phân tích khái niệm "giao tiếp hiệu quả" về các nguyên tắc tâm lý và xã hội học cơ bản nhất.

### `compare()`: So sánh và đối chiếu hai hay nhiều chủ đề

```python
compare(topic1, topic2, context=answer, format="table")
```

**Giải thích:** So sánh và đối chiếu hai hoặc nhiều chủ đề để làm nổi bật những điểm tương đồng và khác biệt cốt lõi. Rất hữu ích khi cần phân biệt các khái niệm dễ nhầm lẫn.

- **Tham số:**
    - `topic1`, `topic2`: Các chủ đề cần so sánh.
    - `context`: Nguồn thông tin. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `format`: Định dạng trình bày kết quả so sánh (`table` - bảng, `list` - danh sách).
- **Ví dụ:**
    - `Compare("SQL", "NoSQL", files, "table")`: Tạo một bảng so sánh chi tiết ưu và nhược điểm của SQL và NoSQL dựa vào nội dung file.

### `five_whys()`: Tìm ra nguyên nhân gốc rễ của một vấn đề bằng cách hỏi "Tại sao?" 5 lần

```python
five_whys(problem, context=answer)
```

- **Giải thích:** Áp dụng kỹ thuật "5 Whys" (5 câu hỏi Tại sao) để tìm ra nguyên nhân gốc rễ của một vấn đề, thay vì chỉ xử lý các triệu chứng bề mặt.
- **Tham số:**
    - `problem`: Vấn đề cần tìm nguyên nhân gốc rễ.
    - `context`: Thông tin nền tảng về vấn đề. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
- **Ví dụ:**
    - `five_whys("Dự án phần mềm bị trễ deadline", files)`: Tìm nguyên nhân gốc rễ thực sự khiến dự án bị trễ dựa trên các báo cáo trong file.

### `devils_advocate()`: Đóng vai người phản biện để tấn công và tìm lỗ hổng trong một lập luận

```python
devils_advocate(argument, context="")
```

**Giải thích:** AI sẽ đóng vai "người phản biện" (devil's advocate). Bạn đưa ra một lập luận, ý tưởng hoặc kết luận, và AI sẽ chủ động tấn công, chỉ ra các lỗ hổng, điểm yếu, và các giả định thiếu cơ sở trong lập luận đó.

- **Tham số:**
    - `argument`: Lập luận, ý tưởng bạn muốn được thử thách.
    - `context`: Thông tin nền tảng (nếu có). Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
- **Ví dụ:**
    - `devils_advocate(argument="Mọi công ty nên cho phép làm việc từ xa hoàn toàn để tăng năng suất.")`: AI sẽ đưa ra các lập luận phản bác như "Làm vậy sẽ ảnh hưởng đến văn hóa công ty, sự sáng tạo ngẫu nhiên và việc đào tạo nhân viên mới thì sao?".

### `thought_experiment()`: Khám phá hệ quả của một kịch bản giả tưởng

```python
thought_experiment(scenario, fields_to_explore)
```

**Giải thích:** Đề xuất một kịch bản giả tưởng (thí nghiệm trong tư duy) và khám phá những hệ quả, tác động có thể xảy ra của nó trên nhiều lĩnh vực khác nhau.

- **Tham số:**
    - `scenario`: Kịch bản giả tưởng.
    - `fields_to_explore`: Các lĩnh vực cần phân tích hệ quả (ví dụ: "sociology, economics, ethics").
- **Ví dụ:**
    - `thought_experiment(scenario="What if humans no longer needed to sleep?", fields_to_explore="economics, psychology, urban planning")`.

### `premortem_analysis()`: Tưởng tượng một dự án, công việc, dự định đã thất bại để tìm ra các rủi ro tiềm ẩn

```python
premortem_analysis(project_description, context="")
```

**Giải thích:** Một kỹ thuật quản lý rủi ro. Thay vì hỏi "dự án này có thể gặp rủi ro gì?", bạn giả định "Dự án này đã thất bại thảm hại" và yêu cầu AI liệt kê tất cả những lý do có thể đã dẫn đến thất bại đó.

- **Tham số:**
    - `project_description`: Mô tả về dự án hoặc kế hoạch sắp thực hiện.
    - `context`: Thông tin bổ sung về bối cảnh. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
- **Ví dụ:**
    - `premortem_analysis(project_description="Launching a new mobile app for language learning")`: AI sẽ liệt kê các lý do "thất bại" như: "Giao diện người dùng quá phức tạp", "Mô hình kinh doanh không bền vững", "Marketing sai đối tượng"...

## Nhóm 6: Ứng dụng Thực tế và Giải quyết Vấn đề

Nhóm này kết nối lý thuyết với thực tiễn, giúp người học áp dụng kiến thức vào các tình huống cụ thể để giải quyết vấn đề.

### `examples()`: Cung cấp các ví dụ thực tế về chủ đề nào đó

```python
examples(topic, quantity=3, format="real_world_scenario", level="intermediate", context=answer)
```

**Giải thích:** Hàm `examples()` được thiết kế để thu hẹp khoảng cách giữa lý thuyết và thực tiễn. Khi học một khái niệm mới, đặc biệt là những khái niệm trừu tượng, việc có được những ví dụ cụ thể, sống động là cực kỳ quan trọng để củng cố sự hiểu biết. Hàm này yêu cầu AI cung cấp một số lượng (`quantity`) ví dụ minh họa về một chủ đề (`topic`) theo một định dạng (`format`) và mức độ phức tạp (`level`) nhất định.

Việc sử dụng hàm này giúp bạn không chỉ "biết" một định nghĩa, mà còn "thấy" được cách khái niệm đó hoạt động trong các bối cảnh khác nhau, từ đó giúp ghi nhớ sâu hơn và có khả năng ứng dụng kiến thức tốt hơn.

- **Tham số:**
    - `topic`: (Bắt buộc) Chủ đề hoặc khái niệm cụ thể bạn muốn lấy ví dụ.
    - `quantity`: (Số nguyên, mặc định là 3) Số lượng ví dụ bạn muốn nhận được.
    - `format`: (Văn bản, mặc định là `real_world_scenario`) Định dạng của ví dụ. Các lựa chọn hữu ích bao gồm:
        - `real_world_scenario`: Các tình huống, ứng dụng trong đời sống và công việc thực tế.
        - `code`: Các đoạn mã nguồn minh họa (dành cho các chủ đề lập trình).
        - `story`: Một câu chuyện ngắn lồng ghép khái niệm.
        - `analogy`: Một phép so sánh, ẩn dụ đơn giản.
        - `data`: Một bộ dữ liệu giả định hoặc một bảng biểu minh họa.
    - `level`: (Văn bản, mặc định là `intermediate`) Mức độ phức tạp của ví dụ, giúp AI điều chỉnh ví dụ cho phù hợp với trình độ của bạn.
        - `beginner`: Dành cho người mới bắt đầu, ví dụ rất đơn giản và trực quan.
        - `intermediate`: Dành cho người đã có kiến thức cơ bản.
        - `expert`: Dành cho người đã có chuyên môn, ví dụ có thể bao gồm các trường hợp phức tạp, ngoại lệ.
    - `context`: (Văn bản, mặc định là `answer`) Nguồn thông tin để AI dựa vào đó tạo ví dụ. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
- **Ví dụ:**
    - `examples("Python Decorators", quantity=2, format="code", level="intermediate")`: Cung cấp 2 ví dụ bằng code ở mức độ trung bình về khái niệm Decorator trong Python.
    - `examples("Confirmation Bias", quantity=1, format="real_world_scenario")`: Cung cấp 1 ví dụ về "Thiên kiến xác nhận" trong một tình huống đời thực.
    - `examples("Newton's Third Law", format="analogy", level="beginner")`: Cung cấp 3 phép so sánh đơn giản, dễ hiểu cho người mới bắt đầu về Định luật 3 của Newton.
    - `examples("Lạm phát", format="data")`: Tạo một bảng dữ liệu đơn giản để minh họa về khái niệm lạm phát qua các năm.

### `real_world()`: Cung cấp các ví dụ về ứng dụng của một chủ đề trong thế giới thực

```python
real_world(topic, context=answer, industry="đa ngành")
```

- Kết nối kiến thức lý thuyết với thực tiễn bằng cách cung cấp các ví dụ cụ thể về cách chủ đề đó được áp dụng trong thế giới thực hoặc một ngành công nghiệp cụ thể.
- **Tham số:**
    - `topic`: Chủ đề cần tìm ứng dụng thực tế.
    - `context`: Nguồn thông tin. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `industry`: Lĩnh vực, ngành nghề cụ thể (ví dụ: "tài chính", "y tế", "giáo dục", "game").
- **Ví dụ:**
    - `real_world("Trí tuệ nhân tạo", "", "y tế")`: Nêu các ví dụ thực tế về ứng dụng của AI trong ngành y tế.

### `create_case_study()`: Tạo ra các tình huống nghiên cứu (case study) để phân tích

```python
create_case_study(field, topic, complexity="detailed", questions_quantity=5)
```

**Giải thích:** Tạo ra một tình huống nghiên cứu (case study) thực tế hoặc giả định, cung cấp đầy đủ bối cảnh, vấn đề, và dữ liệu liên quan. Hàm này rất hữu ích để rèn luyện kỹ năng phân tích, giải quyết vấn đề và ra quyết định.

- **Tham số:**
    - `field`: Lĩnh vực của case study (ví dụ: "business", "marketing", "medicine", "law", "ethics").
    - `topic`: Chủ đề cụ thể của case study (ví dụ: "A failed product launch", "Diagnosing a rare disease").
    - `complexity`: Mức độ phức tạp của tình huống ("simple", "detailed").
    - `questions_quantity`: Số lượng câu hỏi phân tích gợi ý đi kèm case study.
- **Ví dụ:**
    - `create_case_study(field="business", topic="A tech startup facing a giant competitor", complexity="detailed")`: Tạo ra một case study chi tiết về một startup, bao gồm tình hình tài chính, sản phẩm, thị trường và các câu hỏi như "Bạn sẽ làm gì để cạnh tranh?", "Đâu là rủi ro lớn nhất?".

### `role_play_scenario()`: Đặt người học vào một kịch bản đóng vai để rèn luyện kỹ năng mềm

```python
role_play_scenario(scenario, my_role, your_role, objective)
```

**Giải thích:** Thiết lập một tình huống đóng vai tương tác, trong đó bạn và AI đảm nhận các vai trò cụ thể với một mục tiêu rõ ràng. Rất hữu ích để rèn luyện kỹ năng mềm.

- **Tham số:**
    - `scenario`: Bối cảnh của tình huống.
    - `my_role`: Vai trò của bạn.
    - `your_role`: Vai trò của AI.
    - `objective`: Mục tiêu bạn cần đạt được trong kịch bản đó.
- **Ví dụ:**
    - `role_play_scenario(scenario="A salary negotiation", my_role="Employee with 3 years experience", your_role="Hiring Manager", objective="Negotiate a 15% salary increase")`.

### `generate_project_proposal()`: Hướng dẫn cách biến một ý tưởng thành một đề xuất dự án hoàn chỉnh

```python
generate_project_proposal(idea, target_audience, structure="standard")
```

**Giải thích:** Giúp bạn cấu trúc và phác thảo một bản đề xuất dự án hoàn chỉnh từ một ý tưởng ban đầu. Đây là một bài tập tuyệt vời để biến ý tưởng mơ hồ thành kế hoạch hành động.

- **Tham số:**
    - `idea`: Ý tưởng cốt lõi của dự án.
    - `target_audience`: Đối tượng sẽ đọc bản đề xuất (ví dụ: "investors", "a professor", "my manager").
    - `structure`: Cấu trúc của bản đề xuất ("standard" - tiêu chuẩn, "lean_canvas").
- **Ví dụ:**
    - `generate_project_proposal(idea="An app that connects local farmers with consumers", target_audience="investors")`: AI sẽ tạo ra một dàn ý bao gồm các mục như "Problem Statement", "Proposed Solution", "Target Market", "Business Model", "Team"...

### `heuristic_evaluation()`: Đánh giá một đối tượng (VD: website) dựa trên các nguyên tắc chuẩn

```python
heuristic_evaluation(item_to_evaluate, heuristics_set, context=files)
```

**Giải thích:** Đánh giá một đối tượng (ví dụ: giao diện người dùng, một bản thiết kế) dựa trên một bộ các nguyên tắc đã được công nhận (heuristics).

- **Tham số:**
    - `item_to_evaluate`: Thứ cần được đánh giá.
    - `heuristics_set`: Bộ nguyên tắc sử dụng để đánh giá (ví dụ: "Nielsen's 10 Usability Heuristics", "Gestalt Principles of Design").
    - `context`: Nguồn chứa thông tin về đối tượng cần đánh giá (ví dụ: `files` chứa ảnh chụp màn hình). Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
- **Ví dụ:**
    - `heuristic_evaluation(item_to_evaluate="the user registration page", heuristics_set="Nielsen's 10 Usability Heuristics", context=files)`.

### `reverse_engineer()`: Phân tích ngược một sản phẩm để hiểu cách nó được tạo ra

```python
reverse_engineer(outcome, field, components=5)
```

**Giải thích:** Bạn cung cấp kết quả cuối cùng của một quá trình, và AI sẽ cố gắng phân tích ngược lại để phác thảo các bước, quy trình hoặc thành phần có thể đã tạo ra kết quả đó.

- **Tham số:**
    - `outcome`: Kết quả, sản phẩm cuối cùng.
    - `field`: Lĩnh vực của sản phẩm (ví dụ: "software", "marketing campaign", "policy").
    - `components`: Số lượng thành phần/bước chính cần phác thảo.
- **Ví dụ:**
    - `reverse_engineer(outcome="A viral marketing video for a new drink", field="marketing")`: AI sẽ phác thảo các bước có thể như: "1. Nghiên cứu đối tượng mục tiêu. 2. Sáng tạo ý tưởng cốt lõi gây cảm xúc mạnh...".

## Nhóm 7: Hỗ trợ Lập trình và Kỹ thuật

Nhóm này được thiết kế đặc biệt cho việc học các chủ đề kỹ thuật và lập trình, cung cấp các công cụ tương tác và thực hành.

### `explain_code()`: Giải thích chức năng của một đoạn mã

```python
explain_code(context=files, language="", detail_level="line-by-line")
```

**Giải thích:** Giải thích chi tiết một đoạn mã nguồn. AI sẽ phân tích cú pháp, logic và mục đích của từng dòng lệnh hoặc toàn bộ khối mã.

- **Tham số:**
    - `context`: Nơi chứa đoạn mã (thường là `files`). Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `language`: Ngôn ngữ lập trình của đoạn mã (ví dụ: "Python", "JavaScript").
    - `detail_level`: Mức độ chi tiết (`line-by-line` - từng dòng, `overview` - tổng quan về chức năng).
- **Ví dụ:**
    - `explain_code(files, "Python", "overview")`: Giải thích tổng quan về chức năng của đoạn code Python trong file đính kèm.

### `analyze_error()`: Phân tích thông báo lỗi và đề xuất cách sửa

```python
 analyze_error(context=files)
```

**Giải thích:** Phân tích một thông báo lỗi (thường trong lập trình hoặc phần mềm), giải thích nguyên nhân có khả năng nhất gây ra lỗi và đề xuất các giải pháp khả thi để khắc phục.

- **Tham số:**
    - `context`: Nơi chứa thông báo lỗi và các thông tin liên quan (ví dụ: `files` chứa mã nguồn và log lỗi). Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
- **Ví dụ:**
    - `analyze_error(files)`: Phân tích file log lỗi và đoạn code liên quan để tìm ra nguyên nhân và cách sửa lỗi.

### `illustrative_code()`: Viết code để mô phỏng và giải thích một khái niệm trừu tượng

```python
illustrative_code(concept, language="Python", style="simulation")
```

**Giải thích:** Viết một đoạn chương trình hoàn chỉnh không phải để giải quyết một bài toán, mà để mô phỏng và giải thích một ý tưởng, khái niệm trừu tượng. Chương trình sẽ có các chú thích và kết quả đầu ra được thiết kế để làm rõ cách khái niệm đó hoạt động.

- **Tham số:**
    - `concept`: Khái niệm cần được giải thích bằng code (ví dụ: "Recursion", "JavaScript Closures", "Bubble Sort algorithm", "Polymorphism in OOP").
    - `language`: Ngôn ngữ lập trình (ví dụ: "Python", "JavaScript", "Java").
    - `style`: Phong cách minh họa ("simulation" - mô phỏng, "step-by-step" - in ra từng bước, "visual" - tạo output dạng hình ảnh đơn giản).
- **Ví dụ:**
    - `illustrative_code(concept="Dijkstra's Algorithm", language="Python", style="step-by-step")`: Tạo một chương trình Python không chỉ tìm đường đi ngắn nhất mà còn in ra trạng thái của các node ở mỗi bước lặp để giải thích thuật toán.

### `create_colab_tutorial()`: Tạo bài hướng dẫn trên Google Colab kèm bài tập và test case

```python
create_colab_tutorial(topic, libraries, exercises="todo_with_tests")
```

**Giải thích:** Tạo ra nội dung hoàn chỉnh cho một file Google Colab (hoặc Jupyter Notebook), bao gồm các đoạn văn bản giải thích (Markdown), các khối mã lệnh (code cells) để minh họa, và các bài tập thực hành. Đặc biệt, nó có thể tạo bài tập dạng "TODO" và một khối mã chứa các test case (dùng `assert`) để người học tự kiểm tra đáp án.

- **Tham số:**
    - `topic`: Chủ đề của bài hướng dẫn (ví dụ: "Basic Data Analysis with Pandas").
    - `libraries`: Các thư viện cần sử dụng (ví dụ: "pandas, numpy, matplotlib").
    - `exercises`: Loại bài tập ("todo_with_tests" - bài tập có test case, "open_ended" - câu hỏi mở).
- **Ví dụ:**
    - `create_colab_tutorial(topic="Introduction to TensorFlow", libraries="tensorflow, numpy", exercises="todo_with_tests")`: Tạo ra một notebook hướng dẫn về TensorFlow, có phần để trống yêu cầu người học xây dựng một mô hình đơn giản và có code để kiểm tra xem mô hình đó có chạy đúng không.

### `refactor_coach()`: Đề xuất cách cải thiện và tái cấu trúc một đoạn mã

```python
refactor_coach(context=files, language, objective="readability")
```

**Giải thích:** Bạn cung cấp một đoạn code đang hoạt động, AI sẽ phân tích và đề xuất các cách tái cấu trúc (refactor) mã để cải thiện nó theo một mục tiêu cụ thể, kèm theo giải thích lý do tại sao thay đổi đó lại tốt hơn.

- **Tham số:**
    - `context`: Nơi chứa đoạn mã (`files`). Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `language`: Ngôn ngữ lập trình.
    - `objective`: Mục tiêu của việc tái cấu trúc ("readability" - dễ đọc, "performance" - hiệu năng, "maintainability" - dễ bảo trì).
- **Ví dụ:**
    - `refactor_coach(context=files, language="Python", objective="performance")`: AI sẽ đề xuất các thay đổi trong code Python để nó chạy nhanh hơn.

### `tutorial()`: Tạo bài hướng dẫn thực hiện từng bước (step-by-step)

```python
 tutorial(topic, context=answer, target_audience="người mới bắt đầu", steps=7)
```

**Giải thích:** Tạo một bài hướng dẫn chi tiết, từng bước (step-by-step) để thực hiện một công việc hoặc học một kỹ năng nào đó.

- **Tham số:**
    - `topic`: Chủ đề cần tạo bài hướng dẫn.
    - `context`: Nguồn thông tin. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `target_audience`: Đối tượng của bài hướng dẫn.
    - `steps`: Số bước ước tính cho bài hướng dẫn.
- **Ví dụ:**
    - `Tutorial("Cách dùng hàm VLOOKUP trong Excel", files, "nhân viên văn phòng", 5)`: Tạo một bài hướng dẫn 5 bước về cách dùng hàm VLOOKUP cho nhân viên văn phòng, dựa trên file dữ liệu ví dụ.

## Nhóm 8: Phát triển Kỹ năng Học tập Nâng cao

Nhóm này cung cấp các công cụ để người học "học cách học", cải thiện chính phương pháp tư duy và ghi nhớ của mình.

### `elaborate()`: Diễn giải, mở rộng kiến thức và tạo các liên kết sâu hơn

```python
elaborate(topic, context=answer, connections_to="ví dụ thực tế")
```

**Giải thích:** Yêu cầu AI diễn giải, làm rõ và mở rộng một chủ đề bằng cách kết nối nó với các lĩnh vực, khái niệm hoặc thông tin khác. Giúp xây dựng một mạng lưới kiến thức chặt chẽ.

- **Tham số:**
    - `topic`: Chủ đề cần diễn giải.
    - `context`: Nguồn thông tin. Nếu `context=answer`, thông tin sẽ từ chính câu trả lời. Nếu `context=files`, thông tin lấy từ files đính kèm. Nếu `context=prompt`, thông tin sẽ lấy từ chính nội dung prompt. Nếu `context=url`, thông tin sẽ lấy từ địa chỉ url trong prompt.
    - `connections_to`: Lĩnh vực cần kết nối tới (ví dụ: "lịch sử hình thành", "các khái niệm liên quan", "ứng dụng trong đời sống").
- **Ví dụ:**
    - `elaborate("Thuyết tương đối", "", "lịch sử hình thành")`: Diễn giải thuyết tương đối và kết nối nó với bối cảnh lịch sử và khoa học khi nó ra đời.

### `metacognitive_prompt()`: Đưa ra câu hỏi giúp bạn suy nghĩ về chính quá trình tư duy của mình

```python
metacognitive_prompt(topic, my_understanding)
```

**Giải thích:** Đưa ra những câu hỏi giúp bạn suy nghĩ về chính quá trình tư duy và học tập của mình (siêu nhận thức). Giúp bạn tự nhận biết những lỗ hổng kiến thức và cách cải thiện phương pháp học.

- **Tham số:**
    - `topic`: Chủ đề bạn đang học.
    - `my_understanding`: Mô tả ngắn gọn về sự hiểu biết hoặc khó khăn hiện tại của bạn.
- **Ví dụ:**
    - `metacognitive_prompt(topic="Calculus", my_understanding="I understand derivatives but I'm stuck on integrals.")`: AI có thể hỏi: "Bạn nghĩ mối liên hệ giữa đạo hàm và tích phân là gì? Bạn đã thử hình dung tích phân như một diện tích chưa? Câu hỏi nào bạn nên tự hỏi mình ngay bây giờ?".

### `memory_palace_builder()`: Hướng dẫn xây dựng "cung điện ký ức" để ghi nhớ thông tin

```python
 memory_palace_builder(items_to_remember, location, quantity=5)
```

**Giải thích:** Hướng dẫn bạn xây dựng một "cung điện ký ức" (memory palace), một kỹ thuật ghi nhớ bằng cách liên kết các thông tin cần nhớ với các hình ảnh sống động tại một địa điểm quen thuộc.

- **Tham số:**
    - `items_to_remember`: Danh sách những thứ cần nhớ.
    - `location`: Địa điểm quen thuộc bạn chọn làm cung điện (ví dụ: "my bedroom", "the path from my house to school").
    - `quantity`: Số lượng điểm dừng trong cung điện.
- **Ví dụ:**
    - `memory_palace_builder(items_to_remember="Grocery list: milk, eggs, bread", location="my kitchen")`.
