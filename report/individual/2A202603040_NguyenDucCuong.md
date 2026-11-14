# Báo cáo cá nhân — HoVaTen-MSSV

Đổi tên file theo quy tắc `MSSV_HoTen.md`. Ví dụ: `20241234_NguyenVanAn.md`.

Đoạn video: MOT17-09, 150 frame (frame 1–150), nguồn MOTChallenge, giấy phép CC BY-NC-SA 3.0.

## 0. Thông tin học viên

- Họ tên: Nguyen Duc Cuong
- MSSV:2A202603040
- Mã đề (A/B/C): A
- Email:cuongsher@gmail.com
- Link repository:https://github.com/cuongsher/K5-L2-DAY05-NguyenDucCuong-03040-MOTTracking.git
- Giờ bắt đầu:
- Giờ kết thúc:

## 1. Xem trước đoạn video (CP0)

Ghi **trước khi vẽ**, mỗi người một dòng.

| Mã | Frame xuất hiện | Frame cuối thấy được | Rẽ / dừng / đổi tốc độ ở frame | Bị che ở frame | Ghi chú |
|---|---|---|---|---|---|
| P1 |0 |149 | | | |
| P2 |0 |149 | | | |
| P3 |0 |149 | |38–46 | |
| P4 |0 |145 | |110–135 | |
| P5 |44 |149 | | | |

## 2. Keyframe và thời gian (CP1, CP4)

Số keyframe lấy từ kết quả `src/check_submission.py`.

| Mã | Số keyframe | Keyframe ở frame | Số frame có mặt | Keyframe / 100 frame | Thời gian (phút) | Chỗ khó |
|---|---|---|---|---|---|---|
| P1 |24 |0, 9, 19, 28, 34, 35, 37, 40, 48, 76, 82, 102, 108, 120, 121, 124, 125, 129, 133, 138, 139, 142, 145, 149 |150 |16.0 | | |
| P2 |49 |0, 2, 7, 9, 11, 12, 19, 39, 46, 48, 49, 52, 58, 59, 60, 61, 62, 63, 64, 70, 71, 79, 85, 89, 90, 91, 110, 113, 115, 117, 119, 121, 125, 127, 129, 130, 131, 132, 133, 135, 137, 138, 139, 140, 142, 144, 146, 148, 149 |150 |32.7 | | |
| P3 |71 |0, 1, 10, 11, 14, 15, 16, 17, 18, 20, 21, 26, 28, 29, 34, 47, 48, 50, 52, 53, 54, 60–70, 72, 75, 77, 79, 81, 82, 83, 85, 86, 87, 89, 90, 95, 96, 98, 99, 106, 109, 111–117, 120, 121, 122, 124, 125, 126, 128, 129, 131, 138, 141, 145, 147, 148 |141 |50.4 | | |
| P4 |11 |0, 9, 19, 29, 38, 47, 78, 106, 136, 140, 143 |120 |9.2 | | |
| P5 |40 |44, 48, 51, 54, 55, 57, 59, 62, 68, 69, 72, 75, 92, 94, 96, 97, 99, 107, 109, 112, 115, 117, 119, 121, 122, 123, 125, 128, 129, 132, 135, 137, 138, 140, 141, 142, 145, 146, 148, 149 |106 |37.7 | | |
| **Tổng** |195 | |667 |29.2 | | |

Keyframe / 100 frame của cả bài = 195 ÷ 667 × 100 = 29.2

Bạn đặt keyframe nhiều nhất ở người nào? Vì sao (người đó rẽ, dừng, lại gần camera hay bị che)?

Nhiều nhất ở P3 (71 keyframe, 50.4 / 100 frame, hơi vượt ngưỡng cảnh báo 50). Keyframe dày thành cụm ở frame 14–18, 60–70 và 111–117

## 3. Đoạn bị che (CP2)

Người bị che: `P4`

| Mốc | Frame |
|---|---:|
| Bắt đầu bị che một phần (bật `occluded`) | |
| Mất hẳn (bật `outside`) |110 |
| Hiện lại (tắt `outside`) |136 |
| Thấy rõ trở lại (tắt `occluded`) | |

- Thời gian khuất hẳn: 26 frame = 26 / 30 ≈ 0,87 giây (video 30 fps).
- Quyết định: giữ cùng ID 
- Lý do (trả lời 3 câu: khuất bao lâu so với 60 frame, ngoại hình có khớp, chỗ hiện lại có đúng hướng và tốc độ):

(1) khuất 26 frame, ngắn hơn nhiều so với ngưỡng 60 frame;
(2) ngoại hình có khớp không (quần áo, dáng, màu); 
(3) chỗ hiện lại có đúng hướng và tốc độ đi không;

Ảnh chụp màn hình:

![Trước khi che](images/che_1_truoc.png)
![Giữa đoạn che, thấy cờ trên panel object](images/che_2_giua.png)
![Sau khi hiện lại, cùng ID](images/che_3_sau.png)

## 4. Tự review ID (CP3)

Lượt 1 theo người (đi ngược từ frame 149 về 0 trên CVAT), lượt 2 theo cảnh (nhảy 10 frame). Ít nhất 3 dòng; không có lỗi thì ghi một dòng "đã kiểm hai lượt, không lỗi".

Loại lỗi dùng đúng một trong 7 mã: `id_switch`, `fragmentation`, `lost`, `merge`, `false_track`, `drift`, `flag`.

| Frame | Mã người | Loại lỗi | Mô tả một câu | Phát hiện ở lượt | Đã sửa? |
|---:|---|---|---|---|---|
| | | | | | |
| | | | | | |
| | | | | | |

Tổng hợp số lỗi theo loại:

| `id_switch` | `fragmentation` | `lost` | `merge` | `false_track` | `drift` | `flag` |
|---:|---:|---:|---:|---:|---:|---:|
| | | | | | | |

Lỗi nào chỉ lượt 2 (theo cảnh) mới thấy, lượt 1 (theo người) không thấy? Vì sao?

...

## 5. File xuất và kết quả tự kiểm (CP4)

| Kiểm tra | Kết quả |
|---|---|
| Tên file MOT 1.1 |NguyenDucCuong_mot.zip |
| Tên file CVAT for video 1.1 |NguyenDucCuong_cvat_video.zip |
| Số track ID khác nhau trong `gt/gt.txt` (phải là 5) |5 |
| Frame `outside` không có dòng trong `gt.txt` (đúng / sai) |Đúng |
| Job đã completed trên CVAT máy cá nhân | |

Dán phần tóm tắt in ra từ `src/check_submission.py`:

Số frame in theo CVAT (bắt đầu từ 0). Trong gt.txt, frame_id = frame CVAT + 1.

=== File MOT 1.1: NguyenDucCuong_mot.zip ===
  Số track ID: 5   |   Tổng số box: 667
  [OK]        Đúng 5 track ID.

  Track | Frame có mặt | Số frame | Đoạn vắng (outside)
      1 |   0–149      |      150 | -
      2 |   0–149      |      150 | -
      3 |   0–149      |      141 | 38–46
      4 |   0–145      |      120 | 110–135
      5 |  44–149      |      106 | -

  [CẢNH BÁO]  Track 5: chiều cao box đổi > 30% trong 1 frame ở frame [60]. Kiểm tra box co giật (co box theo phần nhìn thấy?).

=== File CVAT for video 1.1: NguyenDucCuong_cvat_video.zip ===

  Track | Nhãn   | Frame thấy | Keyframe | KF/100 frame | Frame occluded | Lần bật outside
      0 | person |        150 |       24 |         16.0 |              0 |               0
              Track 0: keyframe ở frame [0, 9, 19, 28, 34, 35, 37, 40, 48, 76, 82, 102, 108, 120, 121, 124, 125, 129, 133, 138, 139, 142, 145, 149]
      1 | person |        150 |       49 |         32.7 |             62 |               0
              Track 1: keyframe ở frame [0, 2, 7, 9, 11, 12, 19, 39, 46, 48, 49, 52, 58, 59, 60, 61, 62, 63, 64, 70, 71, 79, 85, 89, 90, 91, 110, 113, 115, 117, 119, 121, 125, 127, 129, 130, 131, 132, 133, 135, 137, 138, 139, 140, 142, 144, 146, 148, 149]
      2 | person |        141 |       71 |         50.4 |             11 |               1
              Track 2: keyframe ở frame [0, 1, 10, 11, 14, 15, 16, 17, 18, 20, 21, 26, 28, 29, 34, 47, 48, 50, 52, 53, 54, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 72, 75, 77, 79, 81, 82, 83, 85, 86, 87, 89, 90, 95, 96, 98, 99, 106, 109, 111, 112, 113, 114, 115, 116, 117, 120, 121, 122, 124, 125, 126, 128, 129, 131, 138, 141, 145, 147, 148]
  [CẢNH BÁO]  Track 2: 50 keyframe / 100 frame > 50. Quá dày, dồn keyframe vào chỗ rẽ / dừng / bị che.
      3 | person |        120 |       11 |          9.2 |             11 |               2
              Track 3: keyframe ở frame [0, 9, 19, 29, 38, 47, 78, 106, 136, 140, 143]
      4 | person |        106 |       40 |         37.7 |             24 |               0
              Track 4: keyframe ở frame [44, 48, 51, 54, 55, 57, 59, 62, 68, 69, 72, 75, 92, 94, 96, 97, 99, 107, 109, 112, 115, 117, 119, 121, 122, 123, 125, 128, 129, 132, 135, 137, 138, 140, 141, 142, 145, 146, 148, 149]

  Tổng: 195 keyframe / 667 frame có mặt = 29.2 keyframe / 100 frame
  [OK]        Đọc được 5 track từ annotations.xml.

=== Tóm tắt ===
  Lỗi: 0   |   Cảnh báo: 2
  Không có lỗi định dạng. Mở CVAT xem lại từng [CẢNH BÁO]; cảnh báo đúng ý bạn thì ghi lý do vào báo cáo.

## 6. Ba câu kết

1. Nếu được gán lại, bạn sẽ đặt keyframe khác ở đâu? Vì sao?

   ...

2. Có chỗ nào bạn không chắc "cùng ID hay ID mới"? Bạn đã quyết định và ghi chú thế nào?

   ...

3. Một lỗi ID trong job của bạn (nếu không còn sót, chọn lỗi đã sửa) có thể làm xe tự lái dự đoán sai chuyển động của người đó như thế nào? Lỗi đó ảnh hưởng MOTA hay IDF1 nhiều hơn?

   ...

## Bonus (nếu làm)

### B1 — Hai người đi sát

...

### B2 — So cách đặt keyframe

| Cách đặt | Số keyframe | Frame trôi nhất | Ghi chú |
|---|---:|---:|---|
| Đều mỗi 30 frame | | | |
| Theo chỗ đổi hướng | | | |

...

### B3 — So với tracker có sẵn

| Frame | Mã người | Tracker làm gì | Nhãn của bạn | Giải thích (đoán rồi sửa / ghép IoU / box score thấp / ngoại hình) |
|---:|---|---|---|---|
| | | | | |
| | | | | |

## 7. Tài liệu tham khảo và công cụ AI đã dùng

...
