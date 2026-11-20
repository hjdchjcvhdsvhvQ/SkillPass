# Avalanche Integration Proof

## 1. Thông tin triển khai

Dự án SkillPass sử dụng Avalanche Fuji C-Chain để triển khai smart contract quản lý chứng chỉ. Các thao tác cấp và thu hồi chứng chỉ được thực hiện thông qua ví MetaMask.

| Hạng mục | Thông tin |
|---|---|
| Network | Avalanche Fuji Testnet |
| Chain ID | 43113 |
| Smart contract | `contracts/SkillPassRegistry.sol` |
| Contract Address | `0x15fa49b4314fa91bcec6a2b40171c9a49ed88610` |
| Deploy transaction | `0x5f52307b2767484a7cbb1284772be26fe1079d1de84ac0b467943e3b152c6d8c` |
| Issuer wallet | `0x0CfD1D0b5a4E5b0421D9c4dD1215BED08492DCef` |

Contract: [View on Snowtrace](https://testnet.snowtrace.io/address/0x15fa49b4314fa91bcec6a2b40171c9a49ed88610)

Deploy transaction: [View transaction](https://testnet.snowtrace.io/tx/0x5f52307b2767484a7cbb1284772be26fe1079d1de84ac0b467943e3b152c6d8c)

## 2. Các giao dịch thử nghiệm

Sau khi triển khai, nhóm thực hiện thử nghiệm chức năng cấp chứng chỉ cho ba trường hợp khác nhau. Tiếp đó, nhóm thử thu hồi chứng chỉ của Le Van C để kiểm tra chức năng Revoke.

| # | Hành động | Tx hash | Snowtrace |
|---|---|---|---|
| 1 | Issue – Nguyen Van A | `0x6b489edaac4170de002a4993e828a8200100a4f9e8a05efc3ee0d788c47685ce` | [View](https://testnet.snowtrace.io/tx/0x6b489edaac4170de002a4993e828a8200100a4f9e8a05efc3ee0d788c47685ce) |
| 2 | Issue – Tran Thi B | `0x50450aaa34bc5cfd55f14af80be040bcbd968bafe8476de32f8419927898443b` | [View](https://testnet.snowtrace.io/tx/0x50450aaa34bc5cfd55f14af80be040bcbd968bafe8476de32f8419927898443b) |
| 3 | Issue – Le Van C | `0xe9622103c202aa5cab8ba81e00bedf26251f145883f11827f4cdc99416886396` | [View](https://testnet.snowtrace.io/tx/0xe9622103c202aa5cab8ba81e00bedf26251f145883f11827f4cdc99416886396) |
| 4 | Revoke – Le Van C | `0x7ed9cf9583779e8b9c276b49d192064b137a4849b607d5470b88b5c2193c52bf` | [View](https://testnet.snowtrace.io/tx/0x7ed9cf9583779e8b9c276b49d192064b137a4849b607d5470b88b5c2193c52bf) |

Các giao dịch trên được kiểm tra trên Snowtrace Fuji và đều hiển thị trạng thái Success.

## 3. Kiểm tra chức năng Verify và Revoke

Nhóm sử dụng chức năng Open Verifier để kiểm tra trạng thái của chứng chỉ sau khi cấp và sau khi thu hồi.

Kết quả kiểm tra:
- Chứng chỉ chưa bị thu hồi được hiển thị là Valid.
- Sau khi thực hiện Revoke, Verifier hiển thị trạng thái Revoked đối với chứng chỉ của Le Van C.

Lưu ý: Giao diện My Credentials vẫn hiển thị nút Revoke sau khi thu hồi, trong khi Open Verifier đã hiển thị Revoked. Đây là điểm cần tiếp tục kiểm tra và đồng bộ trong giao diện.

## 4. Đánh giá

Qua các lần thử nghiệm trên Avalanche Fuji, nhóm đã thực hiện được các thao tác chính của SkillPass gồm cấp chứng chỉ, kiểm tra thông tin và thu hồi chứng chỉ.

Việc lưu giao dịch trên blockchain giúp có thể tra cứu lại lịch sử thao tác thông qua Snowtrace thay vì chỉ dựa vào dữ liệu hiển thị trên giao diện ứng dụng.
