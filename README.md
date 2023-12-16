# MSc_S4_Blockchain_Technology

## Giới thiệu
Môn: Blockchain Technology

GV: Nguyễn Đình Thúc - Blockchian_K32 - thuc@nguyendinh (skype/telegram)

Trợ giảng: 
- Ngô Đình Hy: Coding (3 labs blockchain + 2 labs SC, NFT) -- 30%
- Trần Hà Sơn: Math. (Bài tập hằng tuần - 10 bài) -- 40%

Hình thức thi: vấn đáp -- 30%

Q. Bài tập làm hằng tuần có được sửa và trả lại ko?

Sáng thứ 3, 9h seminar của lớp blockchain chất lượng cao - C23 - ứng dụng blockchain

DAC lab (Decentralized Applied Cryptography) - Phòng I63 hỏi cuốn blockchain thầy vừa viết -- join lab? (seminar hằng tuần nguyên ngày thứ 7, có thể join online)
![](./z4845692464416_cc1db6e3b13de6827c8eab907297957d.jpg)

## 031123
Blockchain Technology = Công nghệ Blockchain
- Công nghệ thuộc về khoa học máy tính, trong đó gồm 2 hướng chính:
    - software
    - hệ thống thông tin: blockchain nghiêng hơn về hướng này

Trong hệ thống thông tin bao gồm: DBMS(hệ thống quản lí dữ liệu) và database (data) -- dữ liệu, mục đích chính của việc tổ chức lại dữ liệu này là để tìm kiếm (search)
- Khi thiết kế dữ liệu để tìm kiếm, ta chú ý đến 2 khía cạnh: 
    - performance (nhanh/chậm)
    - security

Blockchain: mang theo nghĩa là sổ cái và là một cơ sở dữ liệu

Cơ sở dữ liệu lại bao gồm 2 loại:
- cơ sở dữ liệu tập trung (centralized DB): tập trung này không có nghĩa là dữ liệu được lưu tập trung ở một chỗ, mà là được quản lí tập trung bởi 1 người. Như vậy, dữ liệu được lưu phân tán ở nhiều chỗ vẫn có thể là một cơ sở dữ liệu tập trung nếu hoạt động theo cơ chế quản lí bởi một người.
    - khi thiết kế cơ sở dữ liệu, vì tập trung nên:
        - performance cần thiết kế index hợp lí (theo các trường hợp tìm kiếm thường xuyên xảy ra hơn cả)
        - security dễ bị tấn công -> để bảo mật -> ta mã hoá cơ sở dữ liệu này -- E(DB) -- -> nhưng mã hoá xong thì khỏi tìm =)). Vậy mã hoá như nào để có thể tìm kiếm được? -> giải quyết bằng bảo mật cơ sở dữ liệu (access control, encrypt) -> không thật sự thành công cho đến khi blockchain ra đời -> blockchain giải quyết bằng cách decentralized DB (phân tán dữ liệu)

Khi giao dịch, A có 10$, khi A chuyển cho B 8$ thì:
- A chuyển cho B 8$
- **và** A chuyển cho chính A 2$ và đóng phiên giao dịch

-> các khái niệm này được ghi lại trên sổ cái nhằm giải quyết vấn đề minh bạch

Để giải quyết vấn đề security khi chỉ có một sổ cái và có thể bị mất: ta replicate thành n sổ cái =)) (ứng dụng của môn hệ thống phân tán)

Như vậy, giải pháp này sẽ gặp hạn chế của hệ thống phân tán:
    - đó là đồng bộ -> ta giải quyết vấn đề này bằng giải pháp đồng thuận -> cần thời gian đồng thuận -> dẫn đến performance kém =))

![](./z4845787370641_fcfbed2a89c4ee851f1fb8f148cb3e8d.jpg)

Trong blockchain, mỗi block có thể được xem là một trang (page), khi đó, cứ một trang gồm một tập hợp các giao dịch đã xảy ra. Các trang này được xâu chuỗi với nhau (chain) (nếu xâu đứt, tất cả các trang sẽ rời rạc nhau) 

Những node giữ sổ cái gọi là miner node, tất cả mọi thiết bị có thể kết nối mạng đều có thể tham gia vào mạng này và có thể tạo thành 1 node. Nếu thiết bị có tham gia thì gọi là user node. Tất cả (miner node và user node) tạo nên blockchain network và được xem như ngang hàng với nhau (Peer-2-Peer network)

Các miner node gom các giao dịch (TX) lại thành một trang (page). Nếu gom nhanh và gắn nhanh vào chain thì được thưởng. Tiền thưởng (reward) cũng được xem như một giao dịch và cũng được ghi vào một trang. Như vậy, quá trình này có thể được gọi là đúc mới 1 đồng coin nếu thành công.

Khi chuyển ta cần validate, hoạt động này có phí.

reward và validate này được xâu thành một cái game. Game này thu hút người chơi nhằm giữ guồng quay / duy trì network

Một node bao gồm:
1. địa chỉ (tương tự như địa chỉ IP)
2. Signkey để mở khoá tài khoản tương ứng với địa chỉ. Signkey này bao gồm public key và private key

Chain(mối nối) được tạo ra bằng cách băm các record của block trước và block sau và nối lại với nhau (ứng dụng của mật mã học)

Tóm lại, có 3 công nghệ nền tảng tạo nên blockchain gồm:
1. Mật mã học (Cryptography)
2. Mạng ngang hàng (P2P/Peer-2-Peer)
3. Game Theory (Lý thuyết trò chơi): chủ yếu tập trung vào việc đảm bảo không xoá/sửa chữa record trong sổ cái và phòng chống gian lận 

![](./z4845864584492_d5f8b149f3e4ec05a02a24d9117b7831.jpg)
![](./z4845864594002_f6f1b46c4a17510ff091e75f0c4539e4.jpg)

Lưu ý:
- Blockchain: chỉ được thêm -> database sẽ tiến về dzô cực =)) -> tính phí lưu trữ -> vậy cái gì cần được lưu trên blockchain để tối ưu
- Database: tuỳ ứng dụng mà sử dụng tập trung hoặc không tập trung. khi cần minh bạch thì dùng blockchain

## Nhập môn mật mã ứng dụng (Applied Cryptosystem)

Cryptology (mật mã học) = cryptography (dựng mã) + cryptanalysis (thám mã)

crytography = dựng một algorithm nhằm tạo key

cryptanalysis = chủ yếu là phân tích để tìm ra key

Khi tạo key, ta có 2 khái niệm cần phân biệt:
- bảo mật(cryptography): thẻ ngân hàng để trên bàn, nhặt được nhưng không dùng được nhờ bảo mật. Analysis (phân tích lỗ hổng nhằm bảo mật). Bảo mật có thể được dùng để phục vụ mục đích an toàn, nhưng không ai dùng an toàn để phục vụ bảo mật tại xàm =)))
- an toàn (security): tiền bỏ trong két sắt phá được két thì lấy được xiền. hack (dùng sức đâm đầu dô két sắt -> hư được két sắt thì lấy được đồ =))

Định nghĩa hệ mã:

Hệ mã cần được đảm bảo các tính chất sau:
- Nếu không có k thì không có được m
- k và k' phải dễ trao đổi và quản lí
- độc lập với thiết bị (có thể chạy một cách bảo mật ở bất kì máy nào)

Trường hợp 1: k và k'là như nhau. 
- ta gọi mã này là mã đối xứng vì có k ta tìm được k'. 
- symetric cryptosystem, secret key cryptosystem, preshared (qui ước) key cryptosystem
- Hai cái phổ biến: AES, 3DES, dùng để bảo vệ dữ liệu off-chain, 

Trường hợp 2: k khác k'
- ta gọi là asymetric cryptosystem (mã bất đối xứng), public key cryptosystem, 
- khi đó:
    - k là khoá mã hoá, e-encryption
    - k' là khoá giải mã, d-decryption

Nếu dùng e và d xuôi thì nó là hệ mã theo định nghĩa

Nếu dùng e và d ngược lại trong định nghĩa hệ mã thì nó thành chữ ký

Trường hợp 3: E không khả nghịch 
- chỉ muốn giấu -> gọi là hàm băm, cryptographic hash function.
- Ví dụ thường dùng khi hash mật khẩu được lưu trữ trên server

![](./z4854742391391_9e7289f8b621809342d78ec2e40334b1.jpg)

![](./z4854742392212_26ff1c2a203bf4d2e91a0e3f7f4c5aad.jpg)

## 171123
Định lý CRT 
Chứng minh định lí RSA
Ref:
- https://crypto.stackexchange.com/questions/2575/chinese-remainder-theorem-and-rsa
- https://iacr.org/archive/ches2008/51540128/51540128.pdf
- https://vi.wikipedia.org/wiki/RSA_%2528m%25C3%25A3_h%25C3%25B3a%2529
- https://www.di-mgt.com.au/crt_rsa.html

Mã công khai dựa trên DLP 
![Alt text](image.png)

Hệ mã ElGamal (ElGamal CryptoSystems)

DLP - Discrete Logarithm Problem

## 241123
DLP-Based CryptoSystem

![Alt text](image-1.png)

![Alt text](image-2.png)

![Alt text](image-3.png)

![Alt text](image-4.png)

![Alt text](image-5.png)

![Alt text](image-6.png)

![Alt text](image-7.png)

![Alt text](image-8.png)

## 011223 - Bitcoin Network - Ngân hàng ngang hàng

Một số định nghĩa:
1. Bank account
2. Transaction
3. Validation

![Alt text](image-13.png)
![Alt text](image-14.png)

Một số cơ chế hoạt động:
1. Tạo địa chỉ (Address Generation)
2. Xác minh giao dịch (Transaction Validation)

Tạo địa chỉ
![Alt text](image-11.png)
![Alt text](image-12.png)
![Alt text](image-17.png)

Cấu trúc của một Transaction
![Alt text](image-9.png)
![Alt text](image-10.png)

## 081223
Duy trì sổ cái **phi tập trung**

![Alt text](image-15.png)

Proof of Work (PoW) (based on partual inverse hash)

Một số tính chất:
1. Kháng tiền ảnh (Pre-image Resistance), ie. cho y=h(x), không tìm lại được x. Hay hàm 1 chiều, hàm không song ánh
2. Kháng tiền ảnh phụ (Second Pre-image Resistance), ie. đã ký rồi thì không giả mạo được mặc dù chữ kí đơn giản. cho y=h(x), không tìm được x' sao cho h(x')=y (cheating)
3. Kháng đụng độ (Collision Resistance), có 2 đơn 1 đơn 10tr, 1 đơn 10 tỷ, lừa cho ký đơn 10tr rồi lấy nó đi dùng thay cho đơn 10tỷ. Cho (x,x'), không tìm được h(x)=h(x') (fake)

Note: Nonce là số dùng 1 lần, Doc là nội dung 

![Alt text](image-16.png)

Tối ưu hoá chương trình

![Alt text](image-19.png)

![Merkle Tree](image-18.png)

Giao thức thanh toán BIP70

![Alt text](image-20.png)

![Alt text](image-21.png)

Note: dApp = distributed app

Vấn đề: Phí giao dịch có thể cao hơn giá trị hàng hoá trao đổi :v 

=> kỹ thuật multi-sign (nhiều người kí, ie. 2 trong 3 người kí) 

=> kỹ thuật bán lẻ P2P, nếu c chưa có quan hệ với A và B mà có (cha-nel) A - B - E - C thì quá giang qua E để thanh toán -> dẫn đến bài toán tìm đường đi ngắn nhất để thanh toán được, mà chi phí thấp và có thể không cần mở channel mới vì mở mới khá đắt

![Alt text](image-22.png)

DApp Lab 
![DApp Note](image-23.png)

[DApp Lecture Record](https://youtu.be/G00TyvcN99Y)