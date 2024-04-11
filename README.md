# Delivery Dijkstra Algorithm

## Đề bài:

![Bản đồ](https://github.com/cauhamau/Delivery_Dijkstra_Algorithm/blob/master/image.png)

- P1, P2, .... là nhà máy sản xuất
- D1, D2, D3, ... là kho vận chuyển
- C1, C2, ... là khách hàng
- Các số trên mũi tên là phí vận chuyển 1 sản phẩm.
- Tồn kho ở nhà máy và kho vận chuyển là có giới hạn.
  
Tìm đường đi sao cho phí vận chuyển là thấp nhất khi khách hàng C bất kỳ đặt n sản phẩm.

### Ví dụ:

- P1, P2, D1, D2, D3 đều tồn kho 2 sản phẩm.
- Khách hàng C1 đặt 10 sản phẩm.

Đường đi tốt nhất là:

P1 -> D1: 2 (sản phẩm) x 0.3 = 0.6

**D1 -> C1: 4 (sản phẩm) x 1.2 = 4.8**

D3 -> D2: 2 (sản phẩm) x 6 = 12

P2 -> D2: 2 (sản phẩm) x 6 = 12

**D2 -> C1: 6 (sản phẩm) x 3 = 18**

## Ý tưởng:

Sử dụng thuật toán Dijkstra để tìm đường đi ngắn nhất từ các nhà máy và kho vận chuyển đến khách hàng đặt hàng.

### TH1:

- Nếu kho có phí vận chuyển rẻ nhất đủ số lượng thì vận chuyển luôn.

### TH2:

#### Bước 1:

- Bắt cặp 2 kho bất kỳ làm trung gian (vì khách hàng nhận tối đa từ 2 kho vận chuyển), xoá hết đường đi từ các kho khác đến khách hàng.

#### Bước 2:

- Chọn từ nơi có chi phí thấp nhất đến cao nhất, khi nào đủ số lượng thì dừng.

#### Bước 3:

- Lưu kết quả trên lại.
  
Lặp lại Bước 1 cho đến khi chọn hết tất cả các cặp kho vận chuyển.

So sánh kết quả tất cả các trường hợp bắt cặp kho vận chuyển và lấy chi phí thấp nhất.
