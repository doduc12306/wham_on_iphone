**Đây là repo của một app trên iPhone, có chứa một bản chưng cất của WHAM trên iPhone, đã xử lý video để ra được điểm poses**

do phần SLAM được thay bằng AREngine trên iPhone, nên chỉ xử lý được những video quay bằng chính app này.

Bên trong thư mục drive gồm có 4 file: 1 file quay màn hình toàn bộ quá trình (bao gồm cả việc tắt hết các kết nối để đảm bảo việc infer diễn ra offline). 3 files còn lại với tiền tố giống nhau lần lượt là video (*.mp4), dữ liệu từ AREngine (*.json), dữ liệu output của model WHAM (*_wham_output.json).

Hiện tại, tác giả mới chỉ cài đặt phần visualize output 17 khớp chuẩn COCO.

Dữ liệu để visualize output ra cả model SMPL như trong demo của nhóm WHAM cũng đã có sẵn (nhờ pose_6d và root_orient). Tuy nhiên để cài đặt được phần đó thì có 2 hướng: (1) tìm một model dạng .usdz có đủ 24 khớp để tận dụng 3d engine của iOS, hoặc (2) tự tính toán và vẽ lại từ dữ liệu pose_6d (cần căn chỉnh rất nhiều, vì bản chất phần này là các góc quay của khớp chứ không phải toạ độ trong 3d).

Hướng (1) thì tác giả chưa tìm được model nào, và hướng (2) thì tác giả đã thử căn chỉnh, nhưng gần như luôn bị lệch, nguyên nhân vì SMPL thực tế là mô hình dành cho các game vui vẻ, không cần chính xác quá (cỡ game chém hoa quả). 

Chi tiết quá trình chuyển đổi model sang dạng mlpackage, tách các phần của model, chưng cất các model đã có trong utils, tuy nhiên chưa hoàn thiện thật sự vì còn rải rác code trên kaggle và colab. Các file mlpackage trên github hiện đang rỗng ruột do file nặng, phần này sẽ bổ sung sau ^_^
