<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Giống Cây Hữu Cơ - Nông Nghiệp Bền Vững</title>
    <!-- Tải Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Thiết lập cấu hình Tailwind (Organic Green Theme) -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        // Tông Xanh Rêu/Xanh Teal Đậm - Gần gũi với đất đai
                        'accent': '#059669', // Deep Green/Teal
                        // Tông Xanh Mint Nhạt - Mềm mại và dịu mắt
                        'secondary': '#a7f3d0', // Soft Mint/Aqua Green
                        // Nền cực kỳ nhạt, gần như trắng với chút xanh lục
                        'bg-light': '#f0fff4', 
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                }
            }
        }
    </script>
    <style>
        /* Đảm bảo khung video responsive */
        .video-container {
            position: relative;
            width: 100%;
            padding-bottom: 56.25%; /* Tỷ lệ 16:9 */
            height: 0;
        }
        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border-radius: 1rem; /* rounded-xl */
        }
        /* Hiệu ứng focus cho nút (Sử dụng accent mới) */
        .btn-focus:focus {
            box-shadow: 0 0 0 4px rgba(5, 150, 105, 0.5); 
            outline: none;
        }
        /* Style cho card nổi bật - Tăng độ cong và bóng mờ hơn */
        .pop-card {
            transition: all 0.3s ease-in-out;
            transform: translateY(0);
        }
        .pop-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }
    </style>
</head>
<body class="bg-bg-light font-sans text-gray-800">

    <!-- Thanh Điều Hướng (Header) - Dùng màu accent đậm hơn, soft shadow -->
    <header class="bg-accent shadow-lg sticky top-0 z-10">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <!-- Logo/Tên Trang -->
                <a href="#home" class="text-2xl font-bold text-white hover:text-secondary transition duration-300">
                    <span class="text-secondary">🌿</span> Nông Nghiệp Tự Nhiên
                </a>

                <!-- Menu Điều Hướng -->
                <nav class="flex space-x-4">
                    <!-- Nút Nav màu trắng, hover sáng hơn -->
                    <a href="#home" id="nav-home" class="nav-item text-white hover:bg-white hover:text-accent px-3 py-2 rounded-lg font-medium transition duration-300">Trang Chủ</a>
                    <a href="#blog" id="nav-blog" class="nav-item text-white hover:bg-white hover:text-accent px-3 py-2 rounded-lg font-medium transition duration-300">Blog</a>
                    <!-- Nút Liên Hệ dùng Secondary, text màu đậm -->
                    <button onclick="document.getElementById('contact-modal').classList.remove('hidden')" class="bg-secondary text-gray-900 px-4 py-2 rounded-xl hover:bg-green-300 transition duration-300 text-sm font-semibold shadow-md btn-focus">Liên Hệ Đặt Hàng</button>
                </nav>
            </div>
        </div>
    </header>

    <!-- Khu Vực Nội Dung Chính (SPA Content) -->
    <main id="app-content" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-10 min-h-screen">
        <!-- Nội dung sẽ được render bởi JavaScript -->
    </main>

    <!-- Footer - Dùng tông Xanh Đậm hơn -->
    <footer class="bg-gray-700 mt-12 py-8">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center text-white">
            <p class="text-lg font-semibold mb-2 text-secondary">Sức Khỏe Từ Mầm Sống Tự Nhiên</p>
            <p class="text-sm text-gray-400">&copy; 2024 Nông Nghiệp Tự Nhiên. Phát triển vì môi trường.</p>
        </div>
    </footer>

    <!-- Modal Liên Hệ -->
    <div id="contact-modal" class="fixed inset-0 bg-gray-900 bg-opacity-75 hidden flex items-center justify-center p-4 z-50">
        <div class="bg-white rounded-3xl shadow-2xl p-6 w-full max-w-md transform transition-all">
            <div class="flex justify-between items-start mb-4">
                <h3 class="text-2xl font-bold text-accent">Đặt Mua Hạt Giống</h3>
                <button onclick="document.getElementById('contact-modal').classList.add('hidden')" class="text-gray-400 hover:text-accent">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
                </button>
            </div>
            <p class="mb-4 text-gray-600">Vui lòng điền thông tin để được tư vấn và đặt mua giống cây chất lượng cao.</p>
            <form onsubmit="handleOrderSubmit(event)">
                <div class="space-y-4">
                    <input type="text" placeholder="Họ và Tên" required class="w-full p-3 border border-gray-300 rounded-xl focus:ring-accent focus:border-accent">
                    <input type="tel" placeholder="Số Điện Thoại" required class="w-full p-3 border border-gray-300 rounded-xl focus:ring-accent focus:border-accent">
                    <textarea placeholder="Giống muốn mua và Số lượng" rows="3" required class="w-full p-3 border border-gray-300 rounded-xl focus:ring-accent focus:border-accent"></textarea>
                </div>
                <!-- Nút Gửi màu Accent -->
                <button type="submit" class="mt-6 w-full bg-accent text-white py-3 rounded-xl font-semibold hover:bg-green-700 transition duration-300 btn-focus shadow-lg">Gửi Đăng Ký</button>
                <div id="order-message" class="mt-4 p-3 hidden rounded-xl text-center font-medium"></div>
            </form>
        </div>
    </div>


    <script>
        // Dữ liệu mô phỏng (Tổng 9 loại cây)
        const varieties = [
            // Cập nhật màu Placeholder Images sang tông Xanh Lá Organic
            { id: 'ca-chua', name: 'Cà Chua Hữu Cơ', desc: 'Giống cà chua heirloom ngọt tự nhiên, đạt chứng nhận hữu cơ quốc tế.', detail: 'Cà chua này kháng bệnh nấm và sâu đục thân tốt. Quả chín có màu đỏ tươi, vị ngọt đậm và thơm hơn hẳn giống thông thường. Rất phù hợp trồng tại vườn nhà.', benefits: ['Kháng bệnh tốt', 'Năng suất cao (3-4kg/cây)', 'Vị ngọt tự nhiên'], planting: ['Trồng trong đất giàu mùn, pH 6.0-6.8.', 'Tưới 2 lần/ngày (sáng và chiều mát).', 'Cần cọc đỡ khi cây cao 40cm.', 'Bón phân hữu cơ định kỳ 15 ngày/lần.'], image: 'https://placehold.co/800x600/e0ffe5/059669?text=Cà+Chua+Sạch', video: 'https://www.youtube.com/embed/f-uM0r6iV1o?si=fR6eA-uU5mQ5D1xX' },
            { id: 'rau-cai', name: 'Rau Cải Xanh', desc: 'Lá xanh đậm, giòn ngon, giàu vitamin A và K. Thích hợp cho canh tác ngắn ngày.', detail: 'Giống cải này phát triển nhanh, chỉ mất 30-35 ngày từ gieo hạt đến thu hoạch. Có thể trồng quanh năm trong điều kiện khí hậu ôn hòa.', benefits: ['Lớn nhanh (30 ngày)', 'Giàu Vitamin A, K', 'Dễ chăm sóc, thích nghi rộng'], planting: ['Gieo hạt trực tiếp trên luống, khoảng cách 15x15cm.', 'Cần ánh sáng đầy đủ 6-8 giờ/ngày.', 'Bảo vệ khỏi ốc sên và sâu ăn lá bằng biện pháp sinh học.'], image: 'https://placehold.co/800x600/ccfbf1/059669?text=Rau+Cải+Hữu+Cơ', video: 'https://www.youtube.com/embed/f-uM0r6iV1o?si=fR6eA-uU5mQ5D1xX' },
            { id: 'ot-chuong', name: 'Ớt Chuông Ngọt', desc: 'Ớt chuông đủ màu (đỏ, vàng, cam), vị ngọt thanh, dùng để chế biến salad và xào.', detail: 'Cây cho quả lớn, màu sắc rực rỡ, độ dày thịt quả cao. Giống cây này cần nhiều nắng và nhiệt độ ổn định để ra hoa và đậu quả.', benefits: ['Chống chịu sâu bệnh', 'Quả lớn, màu sắc đẹp', 'Hàm lượng Vitamin C cao'], planting: ['Trồng trong chậu hoặc đất luống thoát nước tốt.', 'Giữ ẩm liên tục nhưng không để úng nước.', 'Bón phân kali hữu cơ để hỗ trợ ra hoa và đậu quả.'], image: 'https://placehold.co/800x600/e0ffe5/059669?text=Ớt+Chuông+Organic', video: 'https://www.youtube.com/embed/f-uM0r6iV1o?si=fR6eA-uU5mQ5D1xX' },
            { id: 'hung-que-tay', name: 'Húng Quế Tây (Basil)', desc: 'Giống húng quế lá lớn, mùi thơm đậm, thích hợp làm gia vị và tinh dầu.', detail: 'Húng Quế Tây là loại cây gia vị phổ biến, lá to, giàu tinh dầu. Cây dễ trồng, có thể thu hoạch lá liên tục. Rất tốt cho sức khỏe tiêu hóa và dùng để chế biến các món Ý.', benefits: ['Mùi thơm nồng', 'Lá to, năng suất cao', 'Dễ trồng trong chậu'], planting: ['Gieo hạt trong đất ẩm, sau 7 ngày nảy mầm.', 'Đặt nơi có nắng sáng, tránh nắng gắt buổi trưa.', 'Ngắt ngọn thường xuyên để cây phân nhánh và ra nhiều lá.', 'Tưới nước vừa đủ, tránh để lá bị úng.'], image: 'https://placehold.co/800x600/a7f3d0/059669?text=Húng+Quế+Thơm', video: 'https://www.youtube.com/embed/f-uM0r6iV1o?si=fR6eA-uU5mQ5D1xX' },
            
            { id: 'dua-chuot', name: 'Dưa Chuột', desc: 'Giống dưa chuột dài, vỏ xanh tươi, ít hạt, vị giòn ngọt, chuyên canh tác giàn leo.', detail: 'Dưa chuột leo giàn có khả năng kháng bệnh mốc sương và virut xoăn lá tốt. Cây cần giàn kiên cố để phát triển. Thu hoạch liên tục trong 2 tháng.', benefits: ['Giòn ngọt, ít hạt', 'Kháng bệnh cao', 'Thích hợp cho giàn leo'], planting: ['Gieo hạt trực tiếp, làm giàn chữ A hoặc chữ I.', 'Cần tưới nước đầy đủ vào buổi sáng sớm.', 'Bấm ngọn khi cây có 5-6 lá thật để phân nhánh.'], image: 'https://placehold.co/800x600/ccfbf1/059669?text=Dưa+Chuột+Giòn', video: 'https://www.youtube.com/embed/f-uM0r6iV1o?si=fR6eA-uU5mQ5D1xX' },
            { id: 'diep-xoan', name: 'Rau Diếp Xoăn', desc: 'Lá xoăn, vị hơi đắng nhẹ, rất tốt cho tiêu hóa. Phù hợp làm salad và ăn kèm món nướng.', detail: 'Diếp xoăn là cây ưa mát, phát triển mạnh mẽ vào mùa xuân và thu. Rau có màu xanh thẫm, cuốn bắp chặt khi đủ dinh dưỡng.', benefits: ['Lá giòn, thanh mát', 'Giàu chất xơ', 'Giúp thanh nhiệt, giải độc'], planting: ['Trồng trong đất tơi xốp, giàu hữu cơ.', 'Đảm bảo độ ẩm liên tục.', 'Tránh ánh nắng gay gắt buổi trưa.', 'Thu hoạch sau 40-50 ngày gieo.'], image: 'https://placehold.co/800x600/e0ffe5/059669?text=Diếp+Xoăn+Salad', video: 'https://www.youtube.com/embed/f-uM0r6iV1o?si=fR6eA-uU5mQ5D1xX' },
            { id: 'bi-ngo-mini', name: 'Bí Ngô Mini', desc: 'Kích thước nhỏ gọn, thích hợp trồng chậu hoặc ban công. Quả trang trí và ăn dặm cho bé.', detail: 'Bí ngô mini rất dễ trồng, chỉ cần không gian nhỏ. Quả có thể nặng từ 0.5kg đến 1kg. Vị ngọt dẻo, hàm lượng Beta-carotene cao.', benefits: ['Kích thước nhỏ gọn', 'Quả ngọt, dẻo', 'Giá trị trang trí cao'], planting: ['Trồng trong chậu lớn (ít nhất 20 lít đất).', 'Cần nhiều nắng và bón phân lân định kỳ.', 'Thụ phấn nhân tạo nếu trồng trong nhà kính.'], image: 'https://placehold.co/800x600/e0ffe5/059669?text=Bí+Ngô+Mini', video: 'https://www.youtube.com/embed/f-uM0r6iV1o?si=fR6eA-uU5mQ5D1xX' },
            { id: 'cu-den', name: 'Củ Dền Đỏ', desc: 'Củ tròn, màu đỏ đậm, giàu sắt và Axit Folic. Thích hợp làm nước ép và salad.', detail: 'Củ dền là loại cây trồng lấy củ, củ to, màu đỏ tươi. Cây cần đất tơi xốp, không bị nén chặt để củ phát triển tốt dưới lòng đất.', benefits: ['Giàu Sắt, Axit Folic', 'Màu sắc đẹp mắt', 'Phát triển khỏe mạnh'], planting: ['Gieo hạt trực tiếp trên luống, tỉa cây khi có 3 lá thật.', 'Đất phải tơi xốp, không có sỏi đá.', 'Bón bổ sung tro bếp hoặc vôi để tăng pH đất.'], image: 'https://placehold.co/800x600/ccfbf1/059669?text=Củ+Dền+Sạch', video: 'https://www.youtube.com/embed/f-uM0r6iV1o?si=fR6eA-uU5mQ5D1xX' },
            { id: 'hanh-la', name: 'Hành Lá Tiêu Chuẩn', desc: 'Thân trắng dài, lá xanh tươi, mùi thơm dịu. Dễ trồng và thu hoạch liên tục.', detail: 'Hành lá là cây gia vị không thể thiếu, có thể cắt liên tục để sử dụng. Cây kháng bệnh thối rễ tốt, phù hợp trồng thủy canh hoặc thổ canh.', benefits: ['Thu hoạch liên tục', 'Mùi thơm tự nhiên', 'Kháng thối rễ tốt'], planting: ['Trồng bằng củ nhỏ hoặc gieo hạt.', 'Đặt nơi có nắng nhẹ hoặc ánh sáng tán xạ.', 'Cắt khi lá đạt độ cao 20-25cm, để lại gốc 3cm.'], image: 'https://placehold.co/800x600/a7f3d0/059669?text=Hành+Lá+Xanh', video: 'https://www.youtube.com/embed/f-uM0r6iV1o?si=fR6eA-uU5mQ5D1xX' },
        ];

        const blogPosts = [
            { slug: 'ky-thuat-san-thuong', title: 'Kỹ thuật Trồng Rau Hữu Cơ Trên Sân Thượng', date: '01/01/2025', summary: 'Hướng dẫn chi tiết từng bước để có một vườn rau sạch trên sân thượng gia đình, tận dụng không gian hiệu quả.', content: 'Nội dung bài viết chi tiết về cách chọn đất, chọn chậu, hệ thống tưới và các loại cây phù hợp để trồng hữu cơ trên sân thượng, giúp tối ưu hóa năng suất và giảm thiểu sâu bệnh. Đây là giải pháp xanh cho đô thị.' },
            { slug: 'loi-ich-dat-muon', title: '5 Lợi Ích Không Ngờ Của Đất Giàu Mùn', date: '15/01/2025', summary: 'Tìm hiểu tại sao đất hữu cơ lại quan trọng đối với sức khỏe cây trồng và môi trường xung quanh.', content: 'Đất giàu mùn giúp cải thiện cấu trúc đất, tăng khả năng giữ nước, cung cấp dưỡng chất đa vi lượng, và tạo môi trường sống lý tưởng cho vi sinh vật có lợi. Bài viết phân tích sâu 5 lợi ích then chốt của việc bón mùn.' },
            { slug: 'phong-tru-sau-benh', title: 'Phòng Trừ Sâu Bệnh Tự Nhiên Không Dùng Thuốc', date: '28/01/2025', summary: 'Các mẹo dân gian và khoa học để bảo vệ cây trồng khỏi côn trùng gây hại một cách an toàn và bền vững.', content: 'Các phương pháp như sử dụng dung dịch tỏi ớt, trồng xen canh cây đuổi côn trùng (húng quế, cúc vạn thọ), và sử dụng thiên địch là những giải pháp hiệu quả, thân thiện với môi trường.' },
        ];

        // --- Hàm Xử Lý Định Tuyến (Routing) ---
        const appContent = document.getElementById('app-content');

        /**
         * Render nội dung Trang Chủ.
         */
        function renderHome() {
            appContent.innerHTML = `
                <!-- Banner Chính - Sử dụng bo góc lớn hơn, bóng mờ hơn -->
                <section class="mb-12 bg-white p-6 md:p-12 rounded-3xl shadow-xl border-b-8 border-accent">
                    <div class="md:flex items-center justify-between">
                        <div class="md:w-1/2">
                            <h1 class="text-4xl md:text-5xl font-extrabold text-gray-900 leading-tight mb-4">
                                Bắt Đầu Hành Trình Làm Vườn Hữu Cơ Tinh Khiết
                            </h1>
                            <p class="text-lg text-gray-700 mb-6">
                                Các giống cây trồng thuần chủng, khỏe mạnh, được chọn lọc kỹ lưỡng, đảm bảo năng suất và niềm vui khi làm nông nghiệp sạch, bền vững.
                            </p>
                            <!-- Nút Bo tròn, màu Accent -->
                            <a href="#varieties" class="bg-accent text-white text-lg font-bold px-8 py-3 rounded-full inline-block hover:bg-green-700 transition duration-300 shadow-lg pop-card btn-focus">
                                Khám Phá Hạt Giống
                            </a>
                        </div>
                        <div class="md:w-1/2 mt-8 md:mt-0 md:pl-10">
                            <!-- Image bo góc 3xl -->
                            <img src="https://placehold.co/600x400/ccfbf1/059669?text=Nông+Trại+Xanh+Mát" alt="Vườn Hữu Cơ" class="rounded-3xl shadow-xl object-cover w-full border-4 border-white">
                        </div>
                    </div>
                </section>

                <!-- Lợi Ích Của Giống Hữu Cơ -->
                <section class="py-10 mb-12" id="benefits">
                    <!-- Text color changed to accent -->
                    <h2 class="text-3xl font-bold text-center text-accent mb-10">Tại Sao Chọn Giống Thuần Chủng?</h2>
                    <div class="grid md:grid-cols-3 gap-8 text-center">
                        <!-- Card: bo góc lớn hơn, bóng nhẹ nhàng hơn -->
                        <div class="bg-white p-6 rounded-2xl shadow-lg pop-card border-b-4 border-secondary">
                            <!-- Icon color changed to accent, but using secondary as highlight -->
                            <div class="text-5xl text-accent mb-3">🌱</div>
                            <h3 class="text-xl font-bold mb-2 text-gray-900">100% Thuần Chủng</h3>
                            <p class="text-gray-600">Đảm bảo chất lượng di truyền, cây phát triển ổn định, hương vị trọn vẹn.</p>
                        </div>
                        <div class="bg-white p-6 rounded-2xl shadow-lg pop-card border-b-4 border-secondary">
                            <div class="text-5xl text-accent mb-3">💧</div>
                            <h3 class="text-xl font-bold mb-2 text-gray-900">Khả Năng Thích Nghi</h3>
                            <p class="text-gray-600">Giống được chọn lọc để chống chịu tốt với điều kiện khí hậu Việt Nam.</p>
                        </div>
                        <div class="bg-white p-6 rounded-2xl shadow-lg pop-card border-b-4 border-secondary">
                            <div class="text-5xl text-accent mb-3">🤝</div>
                            <h3 class="text-xl font-bold mb-2 text-gray-900">Hỗ Trợ Trọn Đời</h3>
                            <p class="text-gray-600">Tư vấn kỹ thuật canh tác hữu cơ từ A đến Z, miễn phí, chuyên nghiệp.</p>
                        </div>
                    </div>
                </section>

                <!-- Danh Sách Giống Cây -->
                <section class="pt-6" id="varieties">
                    <h2 class="text-3xl font-bold text-center text-gray-800 mb-10">Bộ Sưu Tập Giống Chất Lượng (${varieties.length} Loại)</h2>
                    <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
                        ${varieties.map(v => `
                            <!-- Card bo góc 2xl -->
                            <div class="bg-white rounded-2xl shadow-xl overflow-hidden pop-card group">
                                <!-- Border color updated to Accent -->
                                <img src="${v.image}" alt="${v.name}" class="w-full h-40 object-cover group-hover:opacity-90 transition duration-500 border-b-4 border-accent">
                                <div class="p-4">
                                    <!-- Text color updated to Accent -->
                                    <h3 class="text-xl font-bold text-accent mb-1">${v.name}</h3>
                                    <p class="text-gray-500 mb-4 text-sm line-clamp-2">${v.desc}</p>
                                    <!-- Button colors and hover updated -->
                                    <a href="#details/${v.id}" class="inline-block bg-accent text-white font-semibold px-4 py-2 rounded-xl text-sm hover:bg-green-700 transition duration-300 btn-focus shadow-md">
                                        Xem Chi Tiết
                                    </a>
                                </div>
                            </div>
                        `).join('')}
                    </div>
                </section>
            `;
        }

        /**
         * Render nội dung Trang Chi Tiết Giống Cây.
         * Thêm Thư Viện Ảnh (Gallery) và làm nổi bật Video.
         * @param {string} id - ID của giống cây.
         */
        function renderDetails(id) {
            const variety = varieties.find(v => v.id === id);

            if (!variety) {
                appContent.innerHTML = `<div class="text-center py-20"><h2 class="text-3xl text-red-600">Không tìm thấy giống cây này.</h2><a href="#home" class="text-accent mt-4 block">Quay lại Trang Chủ</a></div>`;
                return;
            }
            
            // Mảng mô phỏng các ảnh phụ (Gallery)
            const galleryImages = [
                { url: 'https://placehold.co/400x300/e0ffe5/059669?text=Giai+Đoạn+Nảy+Mầm', alt: 'Giai đoạn nảy mầm' },
                { url: 'https://placehold.co/400x300/ccfbf1/059669?text=Cây+Đang+Phát+Triển', alt: 'Cây đang phát triển' },
                { url: 'https://placehold.co/400x300/a7f3d0/059669?text=Sản+Phẩm+Thu+Hoạch', alt: 'Sản phẩm thu hoạch' },
            ];

            appContent.innerHTML = `
                <nav class="mb-6 text-sm text-gray-500">
                    <a href="#home" class="hover:text-accent font-semibold">Trang Chủ</a> &gt; 
                    <span class="font-bold text-accent">${variety.name}</span>
                </nav>

                <!-- Card tổng quan bo góc lớn, bóng mờ -->
                <div class="bg-white p-6 md:p-10 rounded-3xl shadow-2xl border-b-8 border-secondary">
                    <!-- Tiêu đề và Hình ảnh -->
                    <h1 class="text-4xl font-extrabold text-accent mb-6">${variety.name}</h1>
                    
                    <div class="lg:flex lg:space-x-10">
                        <!-- Cột Trái: Hình ảnh, Gallery và Chi tiết -->
                        <div class="lg:w-2/3">
                            <!-- Main Image -->
                            <img src="${variety.image}" alt="Hình ảnh chính ${variety.name}" class="w-full h-auto rounded-2xl shadow-xl border-4 border-gray-100 mb-8">

                            <!-- THƯ VIỆN ẢNH (GALLERY) -->
                            <h2 class="text-3xl font-bold text-accent mb-4 border-b pb-2">Thư Viện Ảnh Sản Phẩm</h2>
                            <div class="grid grid-cols-3 gap-4 mb-10">
                                ${galleryImages.map(img => `
                                    <div class="relative overflow-hidden rounded-xl shadow-lg border-2 border-secondary hover:shadow-2xl transition duration-300">
                                        <img src="${img.url}" alt="${img.alt}" class="w-full h-auto object-cover transition duration-300 transform hover:scale-105">
                                        <div class="absolute inset-0 bg-gray-900 bg-opacity-30 flex items-center justify-center opacity-0 hover:opacity-100 transition duration-300">
                                            <span class="text-white text-xs font-semibold p-1 rounded bg-black bg-opacity-50">${img.alt}</span>
                                        </div>
                                    </div>
                                `).join('')}
                            </div>
                            <!-- KẾT THÚC THƯ VIỆN ẢNH -->

                            <!-- Mô tả chi tiết -->
                            <h2 class="text-3xl font-bold text-accent mb-4 border-b pb-2">Đặc Tính Giống</h2>
                            <p class="text-lg text-gray-700 leading-relaxed mb-8">${variety.detail}</p>

                            <!-- Lợi ích -->
                            <h3 class="text-2xl font-bold text-secondary mb-3">Lợi Ích Độc Đáo</h3>
                            <ul class="list-none space-y-3 text-gray-700 mb-8">
                                <!-- Background secondary/20, text accent -->
                                ${variety.benefits.map(b => `<li class="flex items-start bg-secondary/30 p-3 rounded-xl"><span class="mr-3 text-accent text-xl font-bold">★</span> ${b}</li>`).join('')}
                            </ul>

                            <!-- Hướng Dẫn Trồng (Accordion-style) -->
                            <h3 class="text-2xl font-bold text-accent mb-4">Quy Trình Chăm Sóc Đơn Giản</h3>
                            <div class="space-y-4">
                                ${variety.planting.map((step, index) => `
                                    <!-- Border Accent, Background White -->
                                    <div class="bg-white p-4 rounded-xl shadow-md border-l-4 border-accent">
                                        <p class="font-bold text-gray-800"><span class="text-accent text-lg mr-2">${index + 1}.</span> ${step}</p>
                                    </div>
                                `).join('')}
                            </div>
                        </div>

                        <!-- Cột Phải: Video Hướng dẫn và Mua hàng -->
                        <div class="lg:w-1/3 mt-10 lg:mt-0">
                            <!-- Video Hướng dẫn - Border secondary -->
                            <div class="bg-gray-50 p-5 rounded-2xl shadow-inner border border-secondary mb-8">
                                <h3 class="text-xl font-bold text-accent mb-4">Video Hướng Dẫn Trồng</h3>
                                <div class="video-container shadow-xl">
                                    <iframe 
                                        src="${variety.video}" 
                                        title="Video Hướng Dẫn Trồng ${variety.name}" 
                                        frameborder="0" 
                                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
                                        referrerpolicy="strict-origin-when-cross-origin"
                                        allowfullscreen>
                                    </iframe>
                                </div>
                                <p class="text-sm text-gray-500 mt-3">Mẹo nhỏ từ chuyên gia: Video minh họa chung về kỹ thuật trồng.</p>
                            </div>

                            <!-- Khu vực Mua Giống - Background accent/10, border accent -->
                            <div class="bg-accent/10 p-5 rounded-2xl border-4 border-accent shadow-2xl">
                                <h3 class="text-2xl font-extrabold text-accent mb-3">Cơ Hội Mua Giống</h3>
                                <p class="text-4xl font-extrabold text-secondary mb-4">50K <span class="text-xl text-gray-600">VNĐ / Gói</span></p>
                                <!-- Button color and hover updated -->
                                <button onclick="document.getElementById('contact-modal').classList.remove('hidden')" class="w-full bg-accent text-white text-lg font-bold py-3 rounded-xl hover:bg-green-700 transition duration-300 btn-focus shadow-lg pop-card">
                                    Đặt Hàng Nhanh
                                </button>
                                <p class="text-sm text-center text-gray-600 mt-3 font-semibold">🎁 Tặng kèm Ebook Kỹ thuật hữu cơ khi mua 3 gói trở lên!</p>
                            </div>
                        </div>
                    </div>
                </div>
            `;
        }

        /**
         * Render nội dung Trang Blog.
         */
        function renderBlog() {
            appContent.innerHTML = `
                <!-- Title - Màu Accent, Border Secondary -->
                <h1 class="text-4xl font-extrabold text-accent mb-8 text-center border-b-4 border-secondary inline-block pb-1 px-4 mx-auto">Tạp Chí Nông Dân Tự Nhiên</h1>
                
                <div class="grid md:grid-cols-3 gap-8 mb-12 mt-8">
                    <!-- Mục Blog Chính -->
                    ${blogPosts.map(post => `
                        <!-- Card bo góc 2xl, border top Accent -->
                        <div class="bg-white rounded-2xl shadow-xl pop-card overflow-hidden border-t-8 border-accent p-6 flex flex-col justify-between">
                            <div>
                                <h2 class="text-2xl font-bold text-gray-900 mb-3 hover:text-accent transition duration-300">
                                    <a href="#blog/${post.slug}" class="block">${post.title}</a>
                                </h2>
                                <p class="text-sm text-gray-500 mb-4">Ngày đăng: <span class="font-bold text-accent">${post.date}</span></p>
                                <p class="text-gray-600 mb-5 line-clamp-3">${post.summary}</p>
                            </div>
                            <!-- Text color updated to Accent -->
                            <a href="#blog/${post.slug}" class="text-accent font-bold hover:underline mt-2 inline-block">Đọc Tiếp Chi Tiết &rarr;</a>
                        </div>
                    `).join('')}
                </div>

                <!-- Testimonial Section - Background secondary/20, border accent -->
                <div class="bg-secondary/20 p-8 rounded-2xl shadow-inner border-4 border-accent">
                    <h2 class="text-3xl font-bold text-center text-accent mb-8">Nói Gì Về Chúng Tôi?</h2>
                    <div class="grid md:grid-cols-2 gap-8">
                        <!-- Testimonial Card - Border Accent -->
                        <div class="bg-white p-6 rounded-xl shadow-lg border-l-4 border-accent">
                            <p class="text-gray-700 italic mb-4">"Từ khi dùng hạt giống ở đây, vườn nhà tôi luôn xanh tốt và năng suất cao hơn hẳn. Tôi thích cách họ tư vấn về nông nghiệp tự nhiên!"</p>
                            <p class="font-bold text-gray-800">- Anh Hưng, TP. Hồ Chí Minh</p>
                        </div>
                        <!-- Testimonial 2 - Border Accent -->
                        <div class="bg-white p-6 rounded-xl shadow-lg border-l-4 border-accent">
                            <p class="text-gray-700 italic mb-4">"Tôi rất hài lòng với các bài viết hướng dẫn trồng trọt. Nhờ đó, tôi đã thành công trong việc chuyển sang canh tác hoàn toàn hữu cơ."</p>
                            <p class="font-bold text-gray-800">- Chị Mai, Đồng Nai</p>
                        </div>
                    </div>
                </div>
            `;
        }
        
        /**
         * Render nội dung Trang Chi Tiết Blog.
         * @param {string} slug - Slug của bài viết.
         */
        function renderBlogPost(slug) {
            const post = blogPosts.find(p => p.slug === slug);
        
            if (!post) {
                appContent.innerHTML = `<div class="text-center py-20"><h2 class="text-3xl text-red-600">Không tìm thấy bài viết này.</h2><a href="#blog" class="text-accent mt-4 block">Quay lại Blog</a></div>`;
                return;
            }

            appContent.innerHTML = `
                <nav class="mb-6 text-sm text-gray-500">
                    <a href="#home" class="hover:text-accent font-semibold">Trang Chủ</a> &gt; 
                    <a href="#blog" class="hover:text-accent font-semibold">Blog</a> &gt; 
                    <span class="font-bold text-accent">${post.title}</span>
                </nav>

                <!-- Blog Post Card - Bo góc 3xl, border top Accent -->
                <div class="bg-white p-6 md:p-10 rounded-3xl shadow-2xl border-t-8 border-accent">
                    <h1 class="text-4xl font-extrabold text-accent mb-4">${post.title}</h1>
                    <p class="text-sm text-gray-500 mb-8 border-b pb-4">Ngày đăng: <span class="font-bold text-accent">${post.date}</span></p>
                    
                    <div class="prose max-w-none text-lg text-gray-800 space-y-6">
                        <p>${post.content}</p>
                        <!-- Background secondary/20, border accent -->
                        <p class="mt-8 p-4 bg-secondary/30 rounded-xl border-l-4 border-accent italic font-medium">
                            🌿 Bí quyết: Nông nghiệp hữu cơ cần sự kiên nhẫn và quan sát. Hãy theo dõi cây trồng của bạn mỗi ngày để phát hiện sớm các vấn đề.
                        </p>
                        
                        <h2 class="text-2xl font-bold text-secondary mt-10">Bạn có kinh nghiệm gì?</h2>
                        <p>Hãy cùng nhau xây dựng cộng đồng nông nghiệp sạch. Mọi ý kiến đóng góp đều quý báu!</p>
                        
                        <!-- Button color and hover updated -->
                        <a href="#blog" class="inline-block bg-accent text-white font-bold px-6 py-2 rounded-full hover:bg-green-700 transition duration-300 btn-focus shadow-md mt-6">
                            Quay lại Danh Sách Bài Viết
                        </a>
                    </div>
                </div>
            `;
        }

        // --- Hàm Định Tuyến Chính ---
        function router() {
            try {
                const path = window.location.hash.slice(1) || 'home';
                const [route, id] = path.split('/');

                // Cập nhật trạng thái Active cho Nav
                document.querySelectorAll('.nav-item').forEach(item => {
                    item.classList.remove('text-accent', 'font-bold', 'bg-white');
                    item.classList.add('text-white');
                });
                
                if (route === 'home') {
                    renderHome();
                    document.getElementById('nav-home')?.classList.add('text-accent', 'font-bold', 'bg-white');
                    document.getElementById('nav-home')?.classList.remove('text-white');
                } else if (route === 'details' && id) {
                    renderDetails(id);
                } else if (route === 'blog' && id) {
                    renderBlogPost(id);
                    document.getElementById('nav-blog')?.classList.add('text-accent', 'font-bold', 'bg-white');
                    document.getElementById('nav-blog')?.classList.remove('text-white');
                } else if (route === 'blog') {
                    renderBlog();
                    document.getElementById('nav-blog')?.classList.add('text-accent', 'font-bold', 'bg-white');
                    document.getElementById('nav-blog')?.classList.remove('text-white');
                } else {
                    // Mặc định về trang chủ nếu hash không hợp lệ
                    window.location.hash = '#home';
                }
                window.scrollTo(0, 0); // Cuộn lên đầu trang khi chuyển trang
            } catch (error) {
                console.error("Lỗi trong quá trình định tuyến:", error);
                appContent.innerHTML = `<div class="text-center py-20"><h2 class="text-3xl text-red-600">Đã xảy ra lỗi hệ thống. Vui lòng tải lại trang.</h2></div>`;
            }
        }

        // --- Hàm Xử Lý Sự Kiện ---
        
        /**
         * Xử lý đăng ký mua hàng (mô phỏng)
         */
        function handleOrderSubmit(event) {
            event.preventDefault();
            const messageBox = document.getElementById('order-message');
            messageBox.classList.remove('hidden', 'bg-red-100', 'text-red-700');
            // Background xanh mint nhạt cho thông báo thành công
            messageBox.classList.add('bg-secondary', 'text-gray-900'); 
            messageBox.innerHTML = `Đăng ký thành công! Chúng tôi sẽ liên hệ với bạn qua điện thoại trong vòng 2 giờ làm việc. Cảm ơn bạn đã tin tưởng Nông Nghiệp Tự Nhiên.`;
            
            // Đặt lại form sau 3 giây (mô phỏng)
            setTimeout(() => {
                event.target.reset();
                messageBox.classList.add('hidden');
                document.getElementById('contact-modal').classList.add('hidden');
            }, 3000);
        }

        // --- Khởi tạo ứng dụng ---
        window.addEventListener('hashchange', router);
        window.addEventListener('load', router);

    </script>

</body>
</html>


