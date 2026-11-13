# Báo cáo cá nhân — HoVaTen-MSSV

Đổi tên file theo quy tắc `MSSV_HoTen.md`. Ví dụ: `20241234_NguyenVanAn.md`.

Đoạn video: MOT17-09, 150 frame (frame 1–150), nguồn MOTChallenge, giấy phép CC BY-NC-SA 3.0.

## 0. Thông tin học viên

- Họ tên: Trần Đức Hải  
- MSSV: 2A202603151
- Mã đề (A/B/C): C
- Email: dstranhai24@gmail.com
- Link repository: https://github.com/HaiiTran/K5-L2-DAY05-TranDucHai-2A202603151-MOTTracking
- Giờ bắt đầu:
- Giờ kết thúc:

## 1. Xem trước đoạn video (CP0)

Ghi **trước khi vẽ**, mỗi người một dòng.

| Mã | Frame xuất hiện | Frame cuối thấy được | Rẽ / dừng / đổi tốc độ ở frame | Bị che ở frame | Ghi chú |
|---|---|---|---|---|---|
| P1 | 0 | 149 | - | 42–50 | |
| P2 | 63 | 149 | - | - | |
| P3 | 0 | 149| - | - | |
| P4 | 0 | 105 | 42 | 120–126 | |
| P5 | 0 | 136 | 37 | - | |

## 2. Keyframe và thời gian (CP1, CP4)

Số keyframe lấy từ kết quả `src/check_submission.py`.

| Mã | Số keyframe | Keyframe ở frame | Số frame có mặt | Keyframe / 100 frame | Thời gian (phút) | Chỗ khó |
|---|---|---|---|---|---|---|
| P1 | 23 | 0, 10, 20, 29, 39, 51, 53, 54, 55, 59, 69, 73, 75, 79, 89, 99, 104, 109, 119, 123, 129, 139, 149 | 141 | 16.3 | 30 | - |
| P2 | 16 | 63, 64, 67, 69, 71, 79, 89, 93, 99, 106, 109, 115, 119, 129, 139, 149 | 87 | 18.4 | 15 | - |
| P3 | 20 | 0, 10, 20, 30, 40, 50, 59, 60, 69, 70, 79, 89, 93, 99, 109, 119, 125, 129, 139, 149 | 150 | 13.3 | 15 | - |
| P4 | 13 | 0, 10, 19, 29, 34, 39, 49, 59, 69, 79, 93, 95, 99 | 106 | 12.3 | 15 | - |
| P5 | 38 | 0, 4, 9, 10, 14, 19, 29, 36, 37, 39, 44, 49, 50, 54, 56, 58, 59, 64, 69, 74, 78, 80, 83, 84, 89, 94, 99, 103, 104, 107, 109, 112, 113, 118, 119, 127, 132, 135 | 130 | 29.2 | 15 | thay đổi tốc độ, dang tay rộng |
| **Tổng** | 110 | - | 614 | - | 90 | - |

Keyframe / 100 frame của cả bài = tổng keyframe ÷ tổng số frame có mặt × 100 = 17.9 keyframe / 100 frame

Bạn đặt keyframe nhiều nhất ở người nào? Vì sao (người đó rẽ, dừng, lại gần camera hay bị che)?

- đặt nhiều keyframe nhất ở P5. Vì trong quá trình di chuyển, người đó liên tục thay đổi tư thế và dang tay, đồng thời bước đi người này khá rộng nên phải cắm key dày hơn.

## 3. Đoạn bị che (CP2)

Người bị che: `P1`

| Mốc | Frame |
|---|---:|
| Bắt đầu bị che một phần (bật `occluded`) | 29 |
| Mất hẳn (bật `outside`) | 42 |
| Hiện lại (tắt `outside`) | 51 |
| Thấy rõ trở lại (tắt `occluded`) | 55 |

- Thời gian khuất hẳn: 9 frame = 0.3 giây.
- Quyết định: giữ cùng ID 
- Lý do (trả lời 3 câu: khuất bao lâu so với 60 frame, ngoại hình có khớp, chỗ hiện lại có đúng hướng và tốc độ): khuất 9 frame; ngoại hình khớp về trang phục, dáng người; chỗ hiện lại khớp về hướng và tốc độ.
...

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
| Tên file MOT 1.1 | TranDucHai_mot.zip |
| Tên file CVAT for video 1.1 | TranDucHai_cvat_video.zip |
| Số track ID khác nhau trong `gt/gt.txt` (phải là 5) | 5 |
| Frame `outside` không có dòng trong `gt.txt` (đúng / sai) | đúng |
| Job đã completed trên CVAT máy cá nhân | 1 |

Dán phần tóm tắt in ra từ `src/check_submission.py`:

```text
  Lỗi: 0   |   Cảnh báo: 0
```

## 6. Ba câu kết

1. Nếu được gán lại, bạn sẽ đặt keyframe khác ở đâu? Vì sao?

   Không thay đổi chỗ đặt keyframe vì khá chắc chắn với keyframe hiện tại.

2. Có chỗ nào bạn không chắc "cùng ID hay ID mới"? Bạn đã quyết định và ghi chú thế nào?

   Không có.

3. Một lỗi ID trong job của bạn (nếu không còn sót, chọn lỗi đã sửa) có thể làm xe tự lái dự đoán sai chuyển động của người đó như thế nào? Lỗi đó ảnh hưởng MOTA hay IDF1 nhiều hơn?

   Không có.

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
