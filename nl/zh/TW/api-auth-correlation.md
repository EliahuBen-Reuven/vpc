---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-20"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:DomainName: data-hd-keyref="DomainName"}

# API 及 CLI 呼叫所需的資源授權
{: #resource-authorizations-required-for-api-and-cli-calls}

下表列出與「{{site.data.keyword.cloud}} Virtual Private Cloud 基礎架構」物件互動所需的授權。此資訊對於知道您何時進行 API 呼叫特別有用。以下是使用此表格時需要知道的內容：

_連接_ 或_未連接_ 這些術語指的是資源是否與 VPC 或 VPC 相關聯（直接或間接透過資源的子網路）。未連接的浮動 IP 或「網路 ACL」沒有任何子網路，因此它與任何 VPC 都沒有關聯，所以 VPC 的授權不適用。

* **檢視**及**列出**動作對應於**檢視者**或**操作員**角色。
* **更新**及相關動作對應於**編輯者**或**管理者**角色。
* 資源受到授權的保護，資源參照物件則否（ID、CRN 等等）。


| 資源     | 作業      | 必要授權               |
|--------|--------|---------|
| VPC | 建立 | 檢視該 VPC 的「資源群組」的授權，以及「VPC 資源」的「更新」授權 |
| VPC | 更新、刪除 | VPC 的「更新」授權 |
| VPC | 檢視、列出 | VPC 的「檢視」授權 |
| VPC 預設 ACL、預設 SG | 檢視、列出 | VPC 的「檢視」授權 |
| VPC 位址字首 | 建立、更新、刪除 | VPC 的「更新」授權 |
| VPC 位址字首 | 檢視、列出 | VPC 的「檢視」授權 |
|—————|——————|———————|
| 浮動 IP（未關聯）| 建立、更新、刪除 | 如果在預設資源群組中建立資源，則為所有「帳戶管理服務」上的任何「帳戶」使用者及「檢視」授權。如需設定檢視者存取權的指示，請按一下[這裡](https://{DomainName}/docs/infrastructure/vpc?topic=vpc-managing-user-permissions-for-vpc-resources#setting-up-viewer-access)。**附註：關聯及取消關聯是「浮動 IP 更新」作業的一部分**|
| 浮動 IP（未關聯）| 檢視、列出 | 帳戶使用者 |
| 浮動 IP（相關聯）| 更新 | 相關聯子網路及其 VPC 的「更新」授權（您無法在浮動 IP 相關聯之後，予以「建立」或「刪除」）|
| 浮動 IP（相關聯）| 檢視、列出 | 浮動 IP 的子網路的「檢視」授權 | 
|——————|———————|————————|
| 網路 ACL（未連接）、ACL 規則 | 建立、更新、刪除 | 任何「帳戶」使用者 |
| 網路 ACL（未連接）、ACL 規則 | 檢視、列出 | 任何「帳戶」使用者 |
| 網路 ACL（已連接）、ACL 規則 | 建立、更新、刪除 | 所有已連接子網路及 VPC 的「更新」授權 |
| 網路 ACL（已連接）、ACL 規則 | 檢視、列出 | 至少 1 個已連接子網路及 VPC 的「檢視」授權 |
|——————|———————|————————|
| 公用閘道 | 建立、更新、刪除 | PGW 之 VPC 的「更新」授權 |
| 公用閘道 | 檢視、列出 | PGW 之 VPC 的「檢視」授權 |
|—————————|————————|———————————|
| 地理位置 | 檢視、列出 | 若為地區及區域，為任何「帳戶」使用者 |
|———————|————————|—————————|
| SSH 金鑰 | 建立、更新、刪除 | 任何「帳戶」使用者 |
| SSH 金鑰 | 檢視、列出 | 任何「帳戶」使用者 |
|————————|—————————|————————|
| 子網路 | 建立、更新、刪除 | 子網路之 VPC 的「更新」授權 |
| 子網路 | 檢視、列出 | 子網路之 VPC 的「檢視」授權 |
| 子網路 ACL 或 PGW | 連接、分離 | 子網路之 VPC 的「更新」授權 |
| 子網路 ACL 或 PGW | 檢視、列出 | 子網路之 VPC 的「檢視」授權 |
|——————|—————————|————————|
| 安全群組、SG 規則 | 建立、更新、刪除 | 安全群組之 VPC 的「更新」授權 |
| 安全群組、SG 規則 | 檢視、列出 | 安全群組之 VPC 的「檢視」授權 |
| 安全群組的網路介面 | 建立、更新、刪除 | 安全群組之 VPC（也是 NIC 之 VPC）的「更新」授權 |
| 安全群組的網路介面 | 檢視、列出 | 安全群組之 VPC（也是 NIC 之 VPC）的「檢視」授權 |
|—————————|—————————|—————————|
| 映像檔 | 建立、更新、刪除 | 任何「帳戶」使用者 |
| 映像檔 | 檢視、列出 | 任何「帳戶」使用者 |
| 實例 | 建立、更新、刪除 | 實例之 VPC 的「更新」授權 |
| 實例 | 檢視、列出 | 實例之 VPC 的「檢視」授權 |
| 實例動作、NIC、FIP | 建立、更新、刪除 | 實例之 VPC 的「更新」授權 |
| 實例動作、起始設定、NIC、FIP | 檢視、列出 | 實例之 VPC 的「檢視」授權 |
|————————|——————|————————|
| VPN 閘道 | 建立、更新、刪除 | VPN 的「更新」授權 |
| VPN 閘道 | 檢視、列出 | VPN 的「檢視」授權 |
| VPN 閘道連線 | 建立、更新、刪除 | VPN 的「更新」授權 |
| VPN 閘道連線 | 檢視、列出 | VPN 的「檢視」授權 |
| VPN 閘道 ike_policies、ipsec_policies 及連線 | 建立、更新、刪除 | VPN 的「更新」授權 |
| VPN 閘道 ike_policies、ipsec_policies 及連線 | 檢視、列出 | VPN 的「檢視」授權 |
|————————|——————|————————|
| 負載平衡器 | 建立、更新、刪除 |「負載平衡器」的「更新」授權 |
| 負載平衡器 | 檢視、列出 |「負載平衡器」的「檢視」授權 |
|「負載平衡器」儲存區及接聽器 | 建立、更新、刪除 |「負載平衡器」的「更新」授權 |
|「負載平衡器」儲存區及接聽器 | 檢視、列出 |「負載平衡器」的「檢視」授權 |
|————————|——————|————————|
| 磁區 | 建立、更新、刪除 |「磁區」的「更新」授權
| 磁區 | 檢視、列出 |「磁區」的「檢視」授權 |
| 磁區設定檔 | 檢視、列出 | 任何「帳戶」使用者 |

