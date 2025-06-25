
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quiz Từ Vựng</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background-color: #f0f2f5; /* Light background similar to the image */
            margin: 0;
            padding: 20px;
            box-sizing: border-box;
            background-image: url('https://scontent.fhan15-1.fna.fbcdn.net/v/t1.15752-9/508817678_3872052413086247_8922787907608984063_n.png?stp=dst-png_s640x640&_nc_cat=105&ccb=1-7&_nc_sid=0024fc&_nc_ohc=z7MTi9zGgvgQ7kNvwEQVSiD&_nc_oc=AdkpDbNS9gWgbscbWPHoj1ZWwCt_BWSSo-P2JtAB0B1ypKKkbhkBi0PzVahObP92iGuytmoWN846wuqfYOTTIVzQ&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent.fhan15-1.fna&oh=03_Q7cD2gHiNkVJM9d0yGcNXCwENObPRnhdoVA9cx8oQ58qivaOkw&oe=6883DA60');
            background-size: 5000 px;
            background-repeat: repeat;
        }

        .quiz-container {
            background-color: #8c8c8c; 
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
            text-align: center;
            width: 100%;
            max-width: 550px; 
            color: #fff;
            border: 3px solid rgba(255, 255, 255, 0.4);
            position: relative;
            overflow: hidden; /* Ensure background patterns stay within */
        }

        /* Header style for question number and title */
        .quiz-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            font-size: 1.1em;
            font-weight: bold;
            color: #eee;
        }

        .question-text {
            font-size: 2.2em; /* Kích thước chữ lớn hơn cho từ vựng */
            margin-bottom: 40px;
            color: #fff;
            font-weight: bold;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
        }

        .options-container {
            display: flex;
            flex-direction: column;
            gap: 18px; /* Khoảng cách giữa các nút lựa chọn */
            margin-bottom: 30px;
        }

        .option-btn {
            background-color: #a0d9b6; /* Màu xanh lá nhạt */
            border: 3px solid #6b8e23; /* Viền xanh đậm */
            color: #333;
            padding: 18px 25px; /* Tăng padding để nút lớn hơn */
            border-radius: 35px; /* Bo tròn nút nhiều hơn */
            font-size: 1.2em; /* Kích thước chữ trên nút */
            cursor: pointer;
            transition: background-color 0.3s ease, border-color 0.3s ease, transform 0.1s ease, box-shadow 0.3s ease;
            outline: none;
            font-weight: bold;
            text-shadow: 0.5px 0.5px 1px rgba(255,255,255,0.7);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15); /* Shadow nhẹ nhàng */
        }

        /* Màu các nút khác theo hình ảnh */
        .option-btn:nth-child(2) {
            background-color: #d8e6a1; /* Màu vàng nhạt */
            border: 3px solid #8c9c45;
        }
        .option-btn:nth-child(3) {
            background-color: #f7d58a; /* Màu cam nhạt */
            border: 3px solid #b37e0e;
        }
        .option-btn:nth-child(4) {
            background-color: #f5b0b0; /* Màu hồng nhạt */
            border: 3px solid #b05c5c;
        }

        .option-btn:hover {
            transform: translateY(-3px); /* Hiệu ứng nổi lên khi hover */
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.25);
        }

        .option-btn:active {
            transform: translateY(0);
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.15);
        }

        .option-btn.correct {
            background-color: #4CAF50; /* Xanh lá cây khi đúng */
            border-color: #388E3C;
            color: white;
            box-shadow: 0 4px 10px rgba(76, 175, 80, 0.6); /* Shadow nổi bật */
        }

        .option-btn.incorrect {
            background-color: #f44336; /* Đỏ khi sai */
            border-color: #D32F2F;
            color: white;
            box-shadow: 0 4px 10px rgba(244, 67, 54, 0.6); /* Shadow nổi bật */
        }

        .feedback {
            font-size: 1.4em; /* Kích thước chữ lớn hơn cho phản hồi */
            margin-top: 20px;
            min-height: 30px; /* Giữ khoảng trống cho thông báo */
            color: #fff;
            font-weight: bold;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
        }

        .next-btn, .restart-btn {
            background-color: #6a5acd; /* Màu tím */
            border: none;
            color: white;
            padding: 15px 30px;
            border-radius: 30px;
            font-size: 1.2em;
            cursor: pointer;
            margin-top: 25px;
            transition: background-color 0.3s ease, transform 0.1s ease;
            outline: none;
            font-weight: bold;
            text-shadow: 0.5px 0.5px 1px rgba(0,0,0,0.3);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        .next-btn:hover, .restart-btn:hover {
            background-color: #483d8b; /* Tím đậm hơn khi hover */
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
        }

        .next-btn:active, .restart-btn:active {
            transform: translateY(0);
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
        }

        .restart-btn {
            display: none; /* Ban đầu ẩn nút restart */
            background-color: #28a745; /* Màu xanh lá cho nút restart */
            margin-left: 15px; /* Khoảng cách với nút next nếu cả hai cùng hiện */
        }
    </style>
</head>
<body>
    <div class="quiz-container">
        <div id="quiz-header" class="quiz-header">
            <span id="question-number">Câu 1/314</span>
            <span id="quiz-title">Quiz Từ Vựng</span>
        </div>
        <div id="question-text" class="question-text"></div>
        <div class="options-container">
            <button class="option-btn" id="option1"></button>
            <button class="option-btn" id="option2"></button>
            <button class="option-btn" id="option3"></button>
            <button class="option-btn" id="option4"></button>
        </div>
        <div id="feedback" class="feedback"></div>
        <button id="next-btn" class="next-btn">Câu tiếp theo</button>
        <button id="restart-btn" class="restart-btn">Chơi lại</button>
    </div>

    <script>
        // Function to shuffle an array
        function shuffleArray(array) {
            for (let i = array.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [array[i], array[j]] = [array[j], array[i]];
            }
        }

        // All 314 vocabulary words and their correct meanings from all vocabulary.docx
        // For 'otherMeanings', I will dynamically pick 3 random incorrect meanings from the full list of correct meanings.
        const allCorrectMeanings = [
            "cử chỉ, điệu bộ", "phương tiện, cách thức", "tạo điều kiện, làm cho dễ dàng", "có hệ thống", "huyền thoại, chuyện hoang đường",
            "thấp kém hơn, dưới tầm", "so sánh, tương đối", "nhận thức", "sự khác biệt, sự phân biệt", "nói đùa, châm biếm (một cách nhanh trí)",
            "ám chỉ, ngụ ý", "sự phân loại", "tiến hóa, phát triển", "làm mờ, nhòa", "những điều phức tạp",
            "bắt nguồn từ", "(sự) nắm chắc, hiểu vững", "luân phiên, xen kẽ", "năng lực, khả năng", "truyền đạt",
            "hòa nhập, phù hợp với", "dưới tiêu chuẩn", "điều cấm kỵ", "sự phát biểu, lời nói", "thừa nhận (sai lầm, thất bại)",
            "tiến hành, thực hiện", "sự đa dạng", "dựa trên kinh nghiệm/thực nghiệm", "sự giao nhau, ngã tư", "có thể đo lường được",
            "nhận thức, sự cảm nhận", "sự vượt trội, ưu thế", "lỗi, khuyết điểm", "sự sụp đổ", "các giám đốc điều hành",
            "mang lại, gây ra", "hậu quả, tác động xấu", "sự vi phạm", "sự nghỉ hưu", "hàm ý, tác động",
            "chính, chủ yếu", "đáng kể, lớn lao", "thúc đẩy, quảng bá", "sáng kiến", "chuyên tâm, nhất quán",
            "nhắm vào, có mục tiêu", "nhà cung cấp", "bao gồm, toàn diện", "cam kết", "doanh thu / sự thay thế nhân viên",
            "sự tiêu thụ", "danh tiếng", "tận tâm, cống hiến", "cuối cùng, rốt cuộc", "năng suất",
            "gây sửng sốt, choáng ngợp", "lòng trung thành", "ưu tiên", "nguyên tắc", "tình thế khó xử",
            "tạo điều kiện", "phản đối", "khí quyển", "sự bất thường", "một cách mạnh mẽ, đáng kể",
            "sự biến đổi, tính biến thiên", "yếu tố", "chu kỳ", "sự thay đổi", "khí thải",
            "thúc đẩy, dẫn động", "tiềm năng", "giữ lại", "hấp thụ", "thải ra, phát ra",
            "thay đổi, dao động", "đường xích đạo", "ẩm ướt", "đảo ngược", "có thể đoán trước được",
            "đặc trưng bởi", "sự dư thừa", "giải thích cho, chiếm", "phong phú, dồi dào", "bẫy, giữ lại",
            "sự phân hủy", "hiệu lực, sức mạnh", "xa hoa, lãng phí", "bổ dưỡng", "có tính phân cấp",
            "được quay, nướng", "tính di động", "thực phẩm chính", "hầu như", "quý tộc, cao quý",
            "kính đeo mắt", "huyền thoại, tưởng tượng", "cố gắng hết sức", "sự hấp dẫn", "một cách thường xuyên",
            "ẩm thực", "sự nuôi dưỡng, chất dinh dưỡng", "trang trí công phu", "phát triển mạnh", "viết ra",
            "cuộc chinh phục", "thể loại", "sự tôn kính", "huyền bí", "nổi bật",
            "tính trữ tình", "bài phê bình", "vô đạo đức", "nghiêm trọng, khắt khe", "sự miêu tả",
            "hoang phí, xa hoa", "tu viện", "giáo dân, người không chuyên", "giới tu sĩ", "sự dao động",
            "tuổi thọ", "làm gãy, rạn nứt", "mô phỏng", "độ bền", "đồng tình, đồng ý",
            "không thể tái tạo", "có lợi, thuận lợi", "khí thải", "mới lạ", "được ban hành luật",
            "thành phần", "sự giảm bớt", "toàn diện", "mang rủi ro", "bộ lọc",
            "sự ô nhiễm", "đầy hứa hẹn", "khả thi", "nuôi dưỡng", "cửa hàng, nơi tiêu thụ",
            "đáng chú ý", "được cấu tạo từ", "miếng trám (răng)", "hàm răng giả", "vị trí",
            "sự xuống cấp, suy giảm", "thuộc về thẩm mỹ", "thuộc về chỉnh hình", "sự linh hoạt, đa năng", "cho phép, làm cho có thể",
            "đảm bảo", "dữ liệu đầu vào", "điều vô nghĩa", "tinh tế, khó nhận ra", "gợi ý, dấu hiệu",
            "trước khi", "phổ quát, toàn cầu", "thu hút", "xu hướng chủ đạo", "người ủng hộ, tín đồ",
            "tùy tiện, độc đoán", "bao quát, sâu rộng", "tiếp tục từ đó", "bẩm sinh", "dựa trên kinh nghiệm/thực nghiệm",
            "một cách riêng biệt", "không chắc chắn, đáng ngờ", "ranh giới", "nhận thức", "cho là, phỏng đoán",
            "ràng buộc, giới hạn", "bổ sung lẫn nhau", "xâu chuỗi lại với nhau", "rung động", "sự hạn chế",
            "lỗ rỗng, hốc (răng)", "thuộc sinh lý", "thắt lại, co lại", "cách thức", "tiếng lách cách",
            "rõ ràng, hiển nhiên", "chiều, khía cạnh", "sự mong đợi", "vô hình", "quan điểm",
            "đúng giờ", "cơ bản, nền tảng", "nữ tính", "phân biệt giới tính", "nam tính",
            "khuynh hướng", "đặc điểm", "định kiến, khuôn mẫu", "cứng rắn, mạnh mẽ", "bắt nguồn từ",
            "có tính cạnh tranh", "sự thống trị", "khiêm tốn", "chất lượng cuộc sống", "thuộc vùng Bắc Âu",
            "khuôn mẫu", "cứng rắn - mềm mỏng", "đặc điểm", "sự không chắc chắn", "sự ổn định",
            "sự ghét, ác cảm", "sáng tạo", "sự mơ hồ", "bộ máy quan liêu", "nghiêm khắc",
            "số phận", "sự lạc quan", "bi quan", "dải, phạm vi", "theo đuổi",
            "dao động", "sản lượng", "chặn", "rất lớn", "mô (sinh học)",
            "sự tập trung", "mô hình", "thể tích", "nhiệt", "mở rộng",
            "tăng tốc", "sự tan băng", "di dời", "sự dịch chuyển", "sự tuyệt chủng",
            "liên quan", "đa dạng sinh học", "dữ dội", "không thể ở được", "hệ quả",
            "động vật có vú", "sự suy giảm", "bất lợi", "gây ra", "sự bay hơi",
            "sức chứa", "dễ bị tổn thương", "làm trầm trọng thêm", "bão hòa", "sự tận tâm",
            "học thuyết", "kỳ lạ", "sự thử thách", "cuộc tìm kiếm", "ra lệnh",
            "tính xác thực", "sơ đồ mặt bằng", "kẻ xâm lược", "khiêm nhường hơn", "chịu đựng",
            "củng cố", "tiến hóa", "ấn tượng", "kỳ quan", "sự thành thạo",
            "mang tính biểu tượng", "chắc chắn", "phi thường", "rộng rãi", "độc quyền",
            "miêu tả", "vải", "tiền cảnh", "tham gia vào", "cử chỉ",
            "ngụ ý", "sự trùng hợp", "chỉ ra", "tranh chấp", "thay đổi, dao động",
            "đường xích đạo", "ẩm ướt", "đảo ngược", "có thể đoán trước", "lông cừu; vải nỉ",
            "mạch máu; tàu, thuyền", "động mạch", "đang được thực hiện", "thế hệ; sự tạo ra", "đã tinh chế; tao nhã",
            "được dệt", "đầy tham vọng", "nền tảng; bục", "làm trẻ lại", "tác nhân kích thích",
            "một cách tự phát", "được cấy ghép", "vảy (vết thương)", "trục trặc, hư hỏng", "gãy xương",
            "tùy chỉnh", "chữa lành", "gây ra, kích hoạt", "hợp chất, hỗn hợp", "dễ bán, có thể tiêu thụ",
            "mạnh mẽ, cường tráng", "chống lại", "mãn tính", "sáng tạo", "đã thay đổi",
            "cho đến nay", "niên đại", "khấu trừ", "ợ nóng", "can thiệp",
            "ác tính", "nhiệt kế", "kỹ thuật", "hiểu"
        ];

        const questions = [
            { word: "gesture", correctMeaning: "cử chỉ, điệu bộ" },
            { word: "means", correctMeaning: "phương tiện, cách thức" },
            { word: "facilitate", correctMeaning: "tạo điều kiện, làm cho dễ dàng" },
            { word: "systematic", correctMeaning: "có hệ thống" },
            { word: "myth", correctMeaning: "huyền thoại, chuyện hoang đường" },
            { word: "inferior", correctMeaning: "thấp kém hơn, dưới tầm" },
            { word: "comparative", correctMeaning: "so sánh, tương đối" },
            { word: "cognition", correctMeaning: "nhận thức" },
            { word: "distinction", correctMeaning: "sự khác biệt, sự phân biệt" },
            { word: "quipped", correctMeaning: "nói đùa, châm biếm (một cách nhanh trí)" },
            { word: "implying", correctMeaning: "ám chỉ, ngụ ý" },
            { word: "classification", correctMeaning: "sự phân loại" },
            { word: "evolve", correctMeaning: "tiến hóa, phát triển" },
            { word: "blurred", correctMeaning: "làm mờ, nhòa" },
            { word: "complexities", correctMeaning: "những điều phức tạp" },
            { word: "stem from", correctMeaning: "bắt nguồn từ" },
            { word: "(a firm) grasp", correctMeaning: "(sự) nắm chắc, hiểu vững" },
            { word: "alternate", correctMeaning: "luân phiên, xen kẽ" },
            { word: "competence", correctMeaning: "năng lực, khả năng" },
            { word: "convey", correctMeaning: "truyền đạt" },
            { word: "fit in", correctMeaning: "hòa nhập, phù hợp với" },
            { word: "substandard", correctMeaning: "dưới tiêu chuẩn" },
            { word: "taboo", correctMeaning: "điều cấm kỵ" },
            { word: "utterance", correctMeaning: "sự phát biểu, lời nói" },
            { word: "concede", correctMeaning: "thừa nhận (sai lầm, thất bại)" },
            { word: "conduct", correctMeaning: "tiến hành, thực hiện" },
            { word: "diversity", correctMeaning: "sự đa dạng" },
            { word: "empirical", correctMeaning: "dựa trên kinh nghiệm/thực nghiệm" },
            { word: "intersection", correctMeaning: "sự giao nhau, ngã tư" },
            { word: "measurable", correctMeaning: "có thể đo lường được" },
            { word: "perception", correctMeaning: "nhận thức, sự cảm nhận" },
            { word: "superiority", correctMeaning: "sự vượt trội, ưu thế" },
            { word: "defect", correctMeaning: "lỗi, khuyết điểm" },
            { word: "collapse", correctMeaning: "sự sụp đổ" },
            { word: "executives", correctMeaning: "các giám đốc điều hành" },
            { word: "brought about", correctMeaning: "mang lại, gây ra" },
            { word: "repercussions", correctMeaning: "hậu quả, tác động xấu" },
            { word: "violations", correctMeaning: "sự vi phạm" },
            { word: "retirement", correctMeaning: "sự nghỉ hưu" },
            { word: "implications", correctMeaning: "hàm ý, tác động" },
            { word: "primary", correctMeaning: "chính, chủ yếu" },
            { word: "substantial", correctMeaning: "đáng kể, lớn lao" },
            { word: "promoted", correctMeaning: "thúc đẩy, quảng bá" },
            { word: "initiatives", correctMeaning: "sáng kiến" },
            { word: "single-minded", correctMeaning: "chuyên tâm, nhất quán" },
            { word: "targeted", correctMeaning: "nhắm vào, có mục tiêu" },
            { word: "suppliers", correctMeaning: "nhà cung cấp" },
            { word: "inclusive", correctMeaning: "bao gồm, toàn diện" },
            { word: "commitment", correctMeaning: "cam kết" },
            { word: "turnover", correctMeaning: "doanh thu / sự thay thế nhân viên" },
            { word: "consumption", correctMeaning: "sự tiêu thụ" },
            { word: "reputations", correctMeaning: "danh tiếng" },
            { word: "dedicated", correctMeaning: "tận tâm, cống hiến" },
            { word: "ultimately", correctMeaning: "cuối cùng, rốt cuộc" },
            { word: "productivity", correctMeaning: "năng suất" },
            { word: "staggering", correctMeaning: "gây sửng sốt, choáng ngợp" },
            { word: "loyalties", correctMeaning: "lòng trung thành" },
            { word: "prioritize", correctMeaning: "ưu tiên" },
            { word: "principles", correctMeaning: "nguyên tắc" },
            { word: "dilemma", correctMeaning: "tình thế khó xử" },
            { word: "facilitating", correctMeaning: "tạo điều kiện" },
            { word: "be opposed to", correctMeaning: "phản đối" },
            { word: "atmosphere", correctMeaning: "khí quyển" },
            { word: "anomaly", correctMeaning: "sự bất thường" },
            { word: "dramatically", correctMeaning: "một cách mạnh mẽ, đáng kể" },
            { word: "variability", correctMeaning: "sự biến đổi, tính biến thiên" },
            { word: "factors", correctMeaning: "yếu tố" },
            { word: "cycle", correctMeaning: "chu kỳ" },
            { word: "shifts", correctMeaning: "sự thay đổi" },
            { word: "emissions", correctMeaning: "khí thải" },
            { word: "driving", correctMeaning: "thúc đẩy, dẫn động" },
            { word: "potential", correctMeaning: "tiềm năng" },
            { word: "retains", correctMeaning: "giữ lại" },
            { word: "absorb", correctMeaning: "hấp thụ" },
            { word: "emitted", correctMeaning: "thải ra, phát ra" },
            { word: "vary", correctMeaning: "thay đổi, dao động" },
            { word: "equator", correctMeaning: "đường xích đạo" },
            { word: "humid", correctMeaning: "ẩm ướt" },
            { word: "reverse", correctMeaning: "đảo ngược" },
            { word: "predictable", correctMeaning: "có thể đoán trước được" },
            { word: "characterized", correctMeaning: "đặc trưng bởi" },
            { word: "excess", correctMeaning: "sự dư thừa" },
            { word: "account for", correctMeaning: "giải thích cho, chiếm" },
            { word: "abundant", correctMeaning: "phong phú, dồi dào" },
            { word: "trap", correctMeaning: "bẫy, giữ lại" },
            { word: "decay", correctMeaning: "sự phân hủy" },
            { word: "potency", correctMeaning: "hiệu lực, sức mạnh" },
            { word: "lavish", correctMeaning: "xa hoa, lãng phí" },
            { word: "nutritious", correctMeaning: "bổ dưỡng" },
            { word: "hierarchical", correctMeaning: "có tính phân cấp" },
            { word: "roasted", correctMeaning: "được quay, nướng" },
            { word: "mobility", correctMeaning: "tính di động" },
            { word: "staple", correctMeaning: "thực phẩm chính" },
            { word: "virtually", correctMeaning: "hầu như" },
            { word: "noble", correctMeaning: "quý tộc, cao quý" },
            { word: "spectacles", correctMeaning: "kính đeo mắt" },
            { word: "mythical", correctMeaning: "huyền thoại, tưởng tượng" },
            { word: "went to great lengths", correctMeaning: "cố gắng hết sức" },
            { word: "appeal", correctMeaning: "sự hấp dẫn" },
            { word: "on a regular basis", correctMeaning: "một cách thường xuyên" },
            { word: "cuisine", correctMeaning: "ẩm thực" },
            { word: "sustenance", correctMeaning: "sự nuôi dưỡng, chất dinh dưỡng" },
            { word: "ornate", correctMeaning: "trang trí công phu" },
            { word: "flourished", correctMeaning: "phát triển mạnh" },
            { word: "penned", correctMeaning: "viết ra" },
            { word: "conquest", correctMeaning: "cuộc chinh phục" },
            { word: "genres", correctMeaning: "thể loại" },
            { word: "reverence", correctMeaning: "sự tôn kính" },
            { word: "mystical", correctMeaning: "huyền bí" },
            { word: "prominent", correctMeaning: "nổi bật" },
            { word: "lyricism", correctMeaning: "tính trữ tình" },
            { word: "critique", correctMeaning: "bài phê bình" },
            { word: "immoral", correctMeaning: "vô đạo đức" },
            { word: "severely", correctMeaning: "nghiêm trọng, khắt khe" },
            { word: "depiction", correctMeaning: "sự miêu tả" },
            { word: "extravagant", correctMeaning: "hoang phí, xa hoa" },
            { word: "monasteries", correctMeaning: "tu viện" },
            { word: "laypeople", correctMeaning: "giáo dân, người không chuyên" },
            { word: "clergy", correctMeaning: "giới tu sĩ" },
            { word: "fluctuations", correctMeaning: "sự dao động" },
            { word: "longevity", correctMeaning: "tuổi thọ" },
            { word: "fracture", correctMeaning: "làm gãy, rạn nứt" },
            { word: "simulate", correctMeaning: "mô phỏng" },
            { word: "durability", correctMeaning: "độ bền" },
            { word: "concur", correctMeaning: "đồng tình, đồng ý" },
            { word: "nonrenewable", correctMeaning: "không thể tái tạo" },
            { word: "advantageous", correctMeaning: "có lợi, thuận lợi" },
            { word: "emissions", correctMeaning: "khí thải" },
            { word: "novel", correctMeaning: "mới lạ" },
            { word: "legislated", correctMeaning: "được ban hành luật" },
            { word: "components", correctMeaning: "thành phần" },
            { word: "reduction", correctMeaning: "sự giảm bớt" },
            { word: "comprehensive", correctMeaning: "toàn diện" },
            { word: "carry a risk", correctMeaning: "mang rủi ro" },
            { word: "filters", correctMeaning: "bộ lọc" },
            { word: "contamination", correctMeaning: "sự ô nhiễm" },
            { word: "promising", correctMeaning: "đầy hứa hẹn" },
            { word: "viable", correctMeaning: "khả thi" },
            { word: "nourishes", correctMeaning: "nuôi dưỡng" },
            { word: "outlets", correctMeaning: "cửa hàng, nơi tiêu thụ" },
            { word: "noteworthy", correctMeaning: "đáng chú ý" },
            { word: "composed of", correctMeaning: "được cấu tạo từ" },
            { word: "fillings", correctMeaning: "miếng trám (răng)" },
            { word: "denture", correctMeaning: "hàm răng giả" },
            { word: "position", correctMeaning: "vị trí" },
            { word: "deterioration", correctMeaning: "sự xuống cấp, suy giảm" },
            { word: "aesthetic", correctMeaning: "thuộc về thẩm mỹ" },
            { word: "orthopedic", correctMeaning: "thuộc về chỉnh hình" },
            { word: "versatility", correctMeaning: "sự linh hoạt, đa năng" },
            { word: "enable", correctMeaning: "cho phép, làm cho có thể" },
            { word: "ensure", correctMeaning: "đảm bảo" },
            { word: "input", correctMeaning: "dữ liệu đầu vào" },
            { word: "nonsense", correctMeaning: "điều vô nghĩa" },
            { word: "subtle", correctMeaning: "tinh tế, khó nhận ra" },
            { word: "cues", correctMeaning: "gợi ý, dấu hiệu" },
            { word: "prior to", correctMeaning: "trước khi" },
            { word: "universal", correctMeaning: "phổ quát, toàn cầu" },
            { word: "draw", correctMeaning: "thu hút" },
            { word: "mainstream", correctMeaning: "xu hướng chủ đạo" },
            { word: "adherents", correctMeaning: "người ủng hộ, tín đồ" },
            { word: "arbitrary", correctMeaning: "tùy tiện, độc đoán" },
            { word: "sweeping", correctMeaning: "bao quát, sâu rộng" },
            { word: "took it from there", correctMeaning: "tiếp tục từ đó" },
            { word: "innate", correctMeaning: "bẩm sinh" },
            { word: "empirical", correctMeaning: "dựa trên kinh nghiệm/thực nghiệm" },
            { word: "in isolation", correctMeaning: "một cách riêng biệt" },
            { word: "iffy", correctMeaning: "không chắc chắn, đáng ngờ" },
            { word: "boundary", correctMeaning: "ranh giới" },
            { word: "cognitive", correctMeaning: "nhận thức" },
            { word: "presumed", correctMeaning: "cho là, phỏng đoán" },
            { word: "constraints", correctMeaning: "ràng buộc, giới hạn" },
            { word: "complementary", correctMeaning: "bổ sung lẫn nhau" },
            { word: "strung together", correctMeaning: "xâu chuỗi lại với nhau" },
            { word: "vibrating", correctMeaning: "rung động" },
            { word: "restriction", correctMeaning: "sự hạn chế" },
            { word: "cavity", correctMeaning: "lỗ rỗng, hốc (răng)" },
            { word: "physiological", correctMeaning: "thuộc sinh lý" },
            { word: "constricts", correctMeaning: "thắt lại, co lại" },
            { word: "manner", correctMeaning: "cách thức" },
            { word: "click", correctMeaning: "tiếng lách cách" },
            { word: "apparent", correctMeaning: "rõ ràng, hiển nhiên" },
            { word: "dimension", correctMeaning: "chiều, khía cạnh" },
            { word: "expectation", correctMeaning: "sự mong đợi" },
            { word: "invisible", correctMeaning: "vô hình" },
            { word: "perspective", correctMeaning: "quan điểm" },
            { word: "punctuality", correctMeaning: "đúng giờ" },
            { word: "underlying", correctMeaning: "cơ bản, nền tảng" },
            { word: "feminine", correctMeaning: "nữ tính" },
            { word: "sexist", correctMeaning: "phân biệt giới tính" },
            { word: "masculine", correctMeaning: "nam tính" },
            { word: "tendencies", correctMeaning: "khuynh hướng" },
            { word: "traits", correctMeaning: "đặc điểm" },
            { word: "stereotypes", correctMeaning: "định kiến, khuôn mẫu" },
            { word: "tough", correctMeaning: "cứng rắn, mạnh mẽ" },
            { word: "derive", correctMeaning: "bắt nguồn từ" },
            { word: "competitive", correctMeaning: "có tính cạnh tranh" },
            { word: "dominance", correctMeaning: "sự thống trị" },
            { word: "modesty", correctMeaning: "khiêm tốn" },
            { word: "quality of life", correctMeaning: "chất lượng cuộc sống" },
            { word: "Scandinavian", correctMeaning: "thuộc vùng Bắc Âu" },
            { word: "stereotypes", correctMeaning: "khuôn mẫu" },
            { word: "tough-tender", correctMeaning: "cứng rắn - mềm mỏng" },
            { word: "traits", correctMeaning: "đặc điểm" },
            { word: "uncertainty", correctMeaning: "sự không chắc chắn" },
            { word: "stability", correctMeaning: "sự ổn định" },
            { word: "aversion", correctMeaning: "sự ghét, ác cảm" },
            { word: "innovative", correctMeaning: "sáng tạo" },
            { word: "ambiguity", correctMeaning: "sự mơ hồ" },
            { word: "bureaucracy", correctMeaning: "bộ máy quan liêu" },
            { word: "strict", correctMeaning: "nghiêm khắc" },
            { word: "destiny", correctMeaning: "số phận" },
            { word: "optimism", correctMeaning: "sự lạc quan" },
            { word: "pessimistic", correctMeaning: "bi quan" },
            { word: "spectrum", correctMeaning: "dải, phạm vi" },
            { word: "pursuing", correctMeaning: "theo đuổi" },
            { word: "fluctuated", correctMeaning: "dao động" },
            { word: "output", correctMeaning: "sản lượng" },
            { word: "block", correctMeaning: "chặn" },
            { word: "massive", correctMeaning: "rất lớn" },
            { word: "tissues", correctMeaning: "mô (sinh học)" },
            { word: "concentration", correctMeaning: "sự tập trung" },
            { word: "models", correctMeaning: "mô hình" },
            { word: "volume", correctMeaning: "thể tích" },
            { word: "thermal", correctMeaning: "nhiệt" },
            { word: "expands", correctMeaning: "mở rộng" },
            { word: "accelerate", correctMeaning: "tăng tốc" },
            { word: "thawing", correctMeaning: "sự tan băng" },
            { word: "relocating", correctMeaning: "di dời" },
            { word: "displacement", correctMeaning: "sự dịch chuyển" },
            { word: "extinction", correctMeaning: "sự tuyệt chủng" },
            { word: "relevant", correctMeaning: "liên quan" },
            { word: "biodiversity", correctMeaning: "đa dạng sinh học" },
            { word: "intense", correctMeaning: "dữ dội" },
            { word: "uninhabitable", correctMeaning: "không thể ở được" },
            { word: "consequential", correctMeaning: "hệ quả" },
            { word: "mammal", correctMeaning: "động vật có vú" },
            { word: "decline", correctMeaning: "sự suy giảm" },
            { word: "adverse", correctMeaning: "bất lợi" },
            { word: "triggering", correctMeaning: "gây ra" },
            { word: "evaporation", correctMeaning: "sự bay hơi" },
            { word: "capacity", correctMeaning: "sức chứa" },
            { word: "vulnerable", correctMeaning: "dễ bị tổn thương" },
            { word: "exacerbated", correctMeaning: "làm trầm trọng thêm" },
            { word: "saturated", correctMeaning: "bão hòa" },
            { word: "devotion", correctMeaning: "sự tận tâm" },
            { word: "doctrine", correctMeaning: "học thuyết" },
            { word: "bizarre", correctMeaning: "kỳ lạ" },
            { word: "ordeals", correctMeaning: "sự thử thách" },
            { word: "quest", correctMeaning: "cuộc tìm kiếm" },
            { word: "dictated", correctMeaning: "ra lệnh" },
            { word: "authenticity", correctMeaning: "tính xác thực" },
            { word: "floor plans", correctMeaning: "sơ đồ mặt bằng" },
            { word: "invaders", correctMeaning: "kẻ xâm lược" },
            { word: "humbler", correctMeaning: "khiêm nhường hơn" },
            { word: "endured", correctMeaning: "chịu đựng" },
            { word: "fortified", correctMeaning: "củng cố" },
            { word: "evolved", correctMeaning: "tiến hóa" },
            { word: "stunning", correctMeaning: "ấn tượng" },
            { word: "wonder", correctMeaning: "kỳ quan" },
            { word: "mastery", correctMeaning: "sự thành thạo" },
            { word: "iconic", correctMeaning: "mang tính biểu tượng" },
            { word: "undoubtedly", correctMeaning: "chắc chắn" },
            { word: "phenomenal", correctMeaning: "phi thường" },
            { word: "extensively", correctMeaning: "rộng rãi" },
            { word: "exclusively", correctMeaning: "độc quyền" },
            { word: "portrayed", correctMeaning: "miêu tả" },
            { word: "textile", correctMeaning: "vải" },
            { word: "foreground", correctMeaning: "tiền cảnh" },
            { word: "engaged in", correctMeaning: "tham gia vào" },
            { word: "gestures", correctMeaning: "cử chỉ" },
            { word: "implies", correctMeaning: "ngụ ý" },
            { word: "coincidence", correctMeaning: "sự trùng hợp" },
            { word: "indicates", correctMeaning: "chỉ ra" },
            { word: "disputed", correctMeaning: "tranh chấp" },
            { word: "vary", correctMeaning: "thay đổi, dao động" },
            { word: "equator", correctMeaning: "đường xích đạo" },
            { word: "humid", correctMeaning: "ẩm ướt" },
            { word: "reverse", correctMeaning: "đảo ngược" },
            { word: "predictable", correctMeaning: "có thể đoán trước" },
            { word: "fleece", correctMeaning: "lông cừu; vải nỉ" },
            { word: "vessel", correctMeaning: "mạch máu; tàu, thuyền" },
            { word: "arteries", correctMeaning: "động mạch" },
            { word: "in the works", correctMeaning: "đang được thực hiện" },
            { word: "generation", correctMeaning: "thế hệ; sự tạo ra" },
            { word: "refined", correctMeaning: "đã tinh chế; tao nhã" },
            { word: "woven", correctMeaning: "được dệt" },
            { word: "ambitious", correctMeaning: "đầy tham vọng" },
            { word: "platform", correctMeaning: "nền tảng; bục" },
            { word: "rejuvenate", correctMeaning: "làm trẻ lại" },
            { word: "stimulus", correctMeaning: "tác nhân kích thích" },
            { word: "spontaneously", correctMeaning: "một cách tự phát" },
            { word: "transplanted", correctMeaning: "được cấy ghép" },
            { word: "scab", correctMeaning: "vảy (vết thương)" },
            { word: "malfunctioning", correctMeaning: "trục trặc, hư hỏng" },
            { word: "fractures", correctMeaning: "gãy xương" },
            { word: "customized", correctMeaning: "tùy chỉnh" },
            { word: "heal", correctMeaning: "chữa lành" },
            { word: "trigger", correctMeaning: "gây ra, kích hoạt" },
            { word: "composite", correctMeaning: "hợp chất, hỗn hợp" },
            { word: "marketable", correctMeaning: "dễ bán, có thể tiêu thụ" },
            { word: "robust", correctMeaning: "mạnh mẽ, cường tráng" },
            { word: "combating", correctMeaning: "chống lại" },
            { word: "chronic", correctMeaning: "mãn tính" },
            { word: "innovative", correctMeaning: "sáng tạo" },
            { word: "altered", correctMeaning: "đã thay đổi" },
            { word: "to date", correctMeaning: "cho đến nay" },
            { word: "chronology", correctMeaning: "niên đại" },
            { word: "deduct", correctMeaning: "khấu trừ" },
            { word: "heartburn", correctMeaning: "ợ nóng" },
            { word: "intervene", correctMeaning: "can thiệp" },
            { word: "malignant", correctMeaning: "ác tính" },
            { word: "thermometer", correctMeaning: "nhiệt kế" },
            { word: "technical", correctMeaning: "kỹ thuật" },
            { word: "understand", correctMeaning: "hiểu" }
        ];


        let currentQuestionIndex = 0;
        let score = 0;
        let shuffledQuestions = [];

        const questionNumberElement = document.getElementById('question-number');
        const questionTextElement = document.getElementById('question-text');
        const optionButtons = [
            document.getElementById('option1'),
            document.getElementById('option2'),
            document.getElementById('option3'),
            document.getElementById('option4')
        ];
        const feedbackElement = document.getElementById('feedback');
        const nextButton = document.getElementById('next-btn');
        const restartButton = document.getElementById('restart-btn');

        function initializeQuiz() {
            // Shuffle the questions at the beginning of each quiz session
            shuffledQuestions = [...questions]; // Create a copy to shuffle
            shuffleArray(shuffledQuestions);
            currentQuestionIndex = 0;
            score = 0;
            restartButton.style.display = 'none';
            nextButton.textContent = 'Câu tiếp theo'; // Reset button text
            nextButton.style.display = 'block'; // Show next button
            loadQuestion();
        }

        function loadQuestion() {
            if (currentQuestionIndex >= shuffledQuestions.length) {
                endQuiz();
                return;
            }

            const currentQuestion = shuffledQuestions[currentQuestionIndex];
            questionTextElement.textContent = currentQuestion.word;
            questionNumberElement.textContent = `Câu ${currentQuestionIndex + 1}/${shuffledQuestions.length}`;
            feedbackElement.textContent = '';
            nextButton.style.display = 'none'; // Hide next button until answer is selected

            // Prepare options: correct answer + 3 random incorrect answers
            let options = [currentQuestion.correctMeaning];
            let incorrectMeaningsPool = allCorrectMeanings.filter(
                meaning => meaning !== currentQuestion.correctMeaning
            );
            shuffleArray(incorrectMeaningsPool);

            for (let i = 0; i < 3; i++) {
                if (incorrectMeaningsPool.length > 0) {
                    options.push(incorrectMeaningsPool.pop());
                } else {
                    // Fallback if not enough distinct incorrect meanings (shouldn't happen with 314 meanings)
                    options.push("Meaning " + (i + 1));
                }
            }
            shuffleArray(options); // Shuffle options for the current question

            optionButtons.forEach((button, index) => {
                button.textContent = options[index];
                button.className = 'option-btn'; // Reset class
                button.onclick = () => checkAnswer(button, currentQuestion.correctMeaning);
                button.disabled = false; // Enable buttons
            });
        }

        function checkAnswer(selectedButton, correctMeaning) {
            const selectedAnswer = selectedButton.textContent;
            
            if (selectedAnswer === correctMeaning) {
                selectedButton.classList.add('correct');
                feedbackElement.textContent = 'GIỎI LẮM CON CỦA TA';
                score++;
            } else {
                selectedButton.classList.add('incorrect');
                feedbackElement.textContent = `ÓC CỨT NGU SAI RỒI CHÓ ƠI: ${correctMeaning}`;
                // Highlight correct answer
                optionButtons.forEach(button => {
                    if (button.textContent === correctMeaning) {
                        button.classList.add('correct');
                    }
                });
            }

            // Disable all options after selection
            optionButtons.forEach(button => {
                button.disabled = true;
            });

            nextButton.style.display = 'block'; // Show next button
            if (currentQuestionIndex === shuffledQuestions.length - 1) {
                nextButton.textContent = 'Xem kết quả';
            }
        }

        function nextQuestion() {
            currentQuestionIndex++;
            loadQuestion();
        }

        function endQuiz() {
            questionTextElement.textContent = `CUỐI CÙNG CŨNG XONG HẢ ÓC CỨTTT ${score}/${shuffledQuestions.length} điểm.`;
            questionNumberElement.textContent = '';
            feedbackElement.textContent = 'NGUUUU';
            nextButton.style.display = 'none'; // Hide next button
            restartButton.style.display = 'block'; // Show restart button

            // Clear and disable options
            optionButtons.forEach(button => {
                button.textContent = '';
                button.className = 'option-btn';
                button.disabled = true;
            });
        }

        // Event Listeners
        nextButton.addEventListener('click', nextQuestion);
        restartButton.addEventListener('click', initializeQuiz);

        // Initial load
        initializeQuiz();
    </script>
</body>
</html>
