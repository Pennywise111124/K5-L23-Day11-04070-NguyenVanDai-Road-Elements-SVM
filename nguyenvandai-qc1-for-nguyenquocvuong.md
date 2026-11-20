# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): nguyenquocvuong        Người kiểm (học viên): nguyenvandai  
Ngày: 2026-11-20                                  Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest): nguyenquocvuong-front.zip, nguyenquocvuong-fisheye.zip (revision 1)  
Số ảnh kiểm: 20 ảnh bắt buộc (A01–A12, B01–B08) (+ 0 ảnh thêm)   Số nhãn đã kiểm (shape + tag): 174 (94 shape + 80 tag)  

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 20 | 0 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 40 | 0 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 28 | 0 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 28 | 0 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 28 | 0 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 28 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 37 | 0 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 15 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 29 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 14 | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 23 | 0 | chính |
| QC1-12 file | lỗi file | 2 | 0 | nhẹ / nặng |

Cách đếm số mục kiểm (từ file của nguyenquocvuong, chỉ 20 ảnh bắt buộc): QC1-01 = số tag camera; QC1-02 = 20 ảnh × 2 vạch (L1, R1); QC1-03/04/05/06 = 28 lane; QC1-07 = 22 drivable + 10 crosswalk + 5 road_curb; QC1-08 = 15 đèn; QC1-09 = 15 đèn + 14 biển; QC1-10 = 14 biển; QC1-11 = 23 shape trên ảnh fisheye; QC1-12 = 2 file.

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| — | — | — | — | — | Không ghi nhận lỗi nào. |

Cảnh báo của `road_check lint` đã được người kiểm mở ảnh đối chiếu và xác định là báo nhầm:

| Mã | Ảnh | Nội dung cảnh báo | Kết luận |
| --- | --- | --- | --- |
| QC1-02 | A05 (L1, R1), A06 (L1, R1), A07 (L1), A08 (L1, R1), A09 (R1), A12 (L1, R1) | thiếu L1/R1 | báo nhầm: ảnh không thấy vạch ở phía đó (chờ coach xác nhận, xem "Ca mơ hồ") |
| QC1-05 | A04, A09, A11 | 2 polyline cùng position | báo nhầm |
| QC1-12 | A11 | điểm lặp liền nhau ở drivable (nhẹ) | báo nhầm |

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| A05 | Không thấy vạch kẻ làn nào. Xác nhận được miễn QC1-02 (L1, R1)? | (chờ coach) |
| A06 | Không thấy vạch ở phía L1 và R1. Xác nhận được miễn QC1-02? | (chờ coach) |
| A07 | Không thấy vạch ở phía L1. Xác nhận được miễn QC1-02? | (chờ coach) |
| A08 | Không thấy vạch ở phía L1 và R1. Xác nhận được miễn QC1-02? | (chờ coach) |
| A09 | Không thấy vạch ở phía R1. Xác nhận được miễn QC1-02? | (chờ coach) |
| A12 | Không thấy vạch ở phía L1 và R1. Xác nhận được miễn QC1-02? | (chờ coach) |

## Quyết định
Lỗi nặng: 0   Lỗi chính: 0 / 174 nhãn = 0 %   Lỗi nhẹ: 0   Ca chờ lead: 6 (A05, A06, A07, A08, A09, A12; đều là QC1-02)  
Quyết định (Release / Hold / Rework): Hold  
Lý do (theo luật của phiếu): không có lỗi nặng đã xác nhận và tỉ lệ lỗi chính 0 % (≤ 5 %), nhưng còn 6 ca QC1-02 đang chờ coach xác nhận là ảnh không thấy vạch; theo luật, ca chưa có lời đáp ảnh hưởng tới kết luận thì là Hold. Nếu coach xác nhận cả 6 ảnh thì chuyển thành Release; nếu coach cho rằng có vạch thì chuyển thành Rework.  

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: thang mức lỗi QC 1 Road v1.0 (docs/qc_severity_road_v1.0.md trong repo của lab).
