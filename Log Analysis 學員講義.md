# Log Analysis 學員講義

###### tags: `Forensic` `LogAnalysis` `JPCERT` `Handson`
:::success
[TOC]
:::

## APT
### Defnition
針對特定組織的信息盜竊和主要針對系統破壞的無情攻擊
:::info
想了解更多APT的資訊，可以點進連結看趨勢科技的介紹
https://blog.trendmicro.com.tw/?p=123
{%youtube RyQiz8AudQo %}
:::
### 典型流程
![](https://i.imgur.com/PQd0D5m.png =300x250)
![flow](https://i.imgur.com/7hSJWtd.png =350x400)

### Stage 1
| 攻擊手法 | 說明 |
| -------- | -------- |
| 有目的性的攻擊電子郵件     | 一種攻擊，該攻擊發送偽裝成與目標組織有關的人員的電子郵件，並試圖執行附件的惡意軟件或將攻擊者定向到攻擊者想要的網站。     |
| 水坑攻擊 | 試圖通過入侵目標組織正常訪問的網站來感染惡意軟體的攻擊|
| 供應鏈攻擊 | 侵入目標組織通常使用的軟體更新分發源的攻擊，並濫用軟體更新功能來發送惡意軟體等。 |
| 域名劫持 | 攻擊會劫持目標組織使用的網站的Domain，並將其定向到攻擊者想要的網站 |

### Stage 2
| 排名 | 系統指令 | 說明|
| -------- | -------- | -------- |
| 1.   | tasklist     | 這個命令列工具顯示了目前在本機或遠端電腦上執行的應用程式和相關聯的工作/處理程序。|
|2.|ver|It prints the name and version of the operating system, the command shell, or in some implementations the version of other commands.|
|3.|ipconfig|控制網路連線的一個命令列工具|
|4.|net time|有些電腦或主機因無法對外連線，所以不能跟外部做時間校正，利用此方法與可對外同步時間的電腦或主機同步時間。|
|5.|systeminfo|生成Windows硬體與軟體操作環境參數的摘要輸出。|
|6.|netstat|顯示作用中 TCP 連線、電腦正在接聽的埠、乙太網路統計資料、IP 路由表、IP、ICMP、TCP 和 UDP 通訊協定的 IPv4 統計資料 ，以及 ipv6、ICMPv6、透過 IPv6 的 TCP 和 UDP 通訊協定的 IPv6 統計資料。 使用時不含參數，此命令會顯示作用中的 TCP 連接。|
|7.|whoami|顯示目前登入本機系統之使用者的使用者、群組及許可權資訊。 如果使用時不含參數， whoami會顯示目前的網域和使用者名稱。|
|8.|nbtstat|顯示 NetBIOS over TCP/IP (NetBT) 通訊協定統計資料、本機電腦和遠端電腦的 NetBIOS 名稱表，以及 NetBIOS 名稱快取。 此命令也可讓您重新整理 NetBIOS 名稱快取，以及在 Windows 網際網路名稱服務中註冊的名稱 (WINS) 。 使用時不含參數，此命令會顯示說明資訊。|
|9.|net start|啟動服務，或顯示已啟動服務的列表。兩個或多個詞組成的服務名|
|10.|set|設定 Windows 部署服務伺服器、預先設置的電腦、映射、映射群組和傳輸伺服器的屬性和屬性。|

### Stage 3
|排名|指令|說明|
|-|-|-|
|1.|dir|顯示目錄的檔案和子目錄清單。|
|2.|ping|藉由傳送網際網路控制訊息通訊協定 (ICMP) echo 要求訊息，來驗證另一部 TCP/IP 電腦的 IP 層級連線能力。 隨即會顯示對應的回應回復訊息的回條，以及來回行程時間。 ping 是用來針對連線能力、連線能力和名稱解析進行疑難排解的主要 TCP/IP 命令。 使用時不含參數，此命令會顯示說明內容。|
|3.|net view|Displays a list of domains, computers, or resources that are being shared by the specified computer.|
|4.|type|在 Windows 命令列介面中，type是內建命令，可顯示文字檔的內容。 使用type命令來查看文字檔，而不加以修改。|
|5.|net use|Connects a computer to or disconnects a computer from a shared resource, or displays information about computer connections. The command also controls persistent net connections. Used without parameters, **net use** retrieves a list of network connections.|
|6.|echo|顯示訊息，或開啟或關閉命令回顯功能。|
|7.|net user|Adds or modifies user accounts, or displays user account information.|
|8.|net group|Adds, displays, or modifies global groups in domains.|
|9.|net localgroup|Adds, displays, or modifies local groups. Used without parameters, **net localgroup** displays the name of the server and the names of local groups on the computer.|
|10.|dsquery|該工具的命令集允許您根據指定的標準查詢目錄。|

![](https://i.imgur.com/STdYuKg.png =300x)

### Stage 4
 - mimikatz
 - PWDump7
 - PWDumpX
 - Quarks PWDump
 - WCE
 - Gsecdump
 - AceHash
 - ![](https://i.imgur.com/Uq8kM1m.png =300x)
:::info
**Mimikatz**
![](https://i.imgur.com/Ycw8mva.png =300x)
:::

:warning: AD元件服務
 - [KDC(Key Distribution Center 金鑰分配中心)](https://doubleoctopus.com/security-wiki/authentication/key-distribution-center/)
 - [Kerberos Key Distribution Center](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc734104(v=ws.10)?redirectedfrom=MSDN)
 - [AS(Authentication Server)](https://www.rebeladmin.com/2018/06/active-directory-authentication-works/)
 -  

:::info
==Know More about the Keywords==
 - [Pass-The-Hash(PTH)](http://www.cyberview.com.tw/wp-content/uploads/2018/04/news02.pdf)
 - [內網滲透Pass the Hash(PtH)攻擊手法及防禦、偵測措施](https://wwwstar.medium.com/%E5%85%A7%E7%B6%B2%E6%BB%B2%E9%80%8F-pass-the-hash-pth-%E6%94%BB%E6%93%8A%E6%89%8B%E6%B3%95%E5%8F%8A%E9%98%B2%E7%A6%A6-%E5%81%B5%E6%B8%AC%E6%8E%AA%E6%96%BD-e1d15e807a67)
 - [Golden Ticket (SecurityWiki)](https://doubleoctopus.com/security-wiki/threats-and-tools/golden-ticket/)
 - [Kerberos Attack: Silver Ticket Edition](https://www.varonis.com/blog/kerberos-attack-silver-ticket/)
 - [域滲透 - Pass the Ticket](https://wooyun.js.org/drops/%E5%9F%9F%E6%B8%97%E9%80%8F%E2%80%94%E2%80%94Pass%20The%20Ticket.html)
:::

| 排名 | 系統指令 | 說明|
| -------- | -------- | -------- |
|1|at|您可以使用 at 命令，排程命令、腳本或程式，以在指定的日期和時間執行。 您也可以使用此命令來查看現有的排程任務。若要使用 at 命令，必須執行工作排程器服務，且必須以本機 Administrators 群組成員的身分登入。 當您使用 at 命令建立工作時，您必須設定任務，使其在相同使用者帳戶中執行。|
|2|move|將一或多個檔案從一個目錄移至另一個目錄。|
|3|schtasks|排程命令和程式定期執行或在特定時間執行、新增和移除排程中的工作、啟動和停止隨選工作，以及顯示和變更排定的工作。|
|4|copy|將一或多個檔案從某個位置複製到另一個位置。|
|5|ren|重新命名檔案或目錄。|
|6|reg|某些作業可讓您在本機或遠端電腦上查看或設定登錄專案，而其他作業則可讓您只設定本機電腦。 使用 reg 來設定遠端電腦的登錄，會限制您可以在某些作業中使用的參數。 檢查每項作業的語法和參數，確認它們可以在遠端電腦上使用。|
|7|wmic|The WMI command-line (WMIC) utility provides a command-line interface for Windows Management Instrumentation (WMI). WMIC is compatible with existing shells and utility commands. The following is a general reference topic for WMIC.|
|8|powershell|執行PowerShell指令|
|9|md|建立目錄或子目錄。 預設會啟用的命令延伸模組可讓您使用單一 md 命令，在指定的路徑中建立中繼目錄。|
|10|runas|Allows a user to run specific tools and programs with different permissions than the user's current logon provides.Runas is a command-line tool that is built into Windows Vista. To use runas at the command line, open a command prompt, type runas with the appropriate parameters, and then press ENTER. In the user interface for Windows Vista, the Run as… command has been changed to Run as administrator. However, you should rarely have to use the Run as administrator command because Windows Vista will automatically prompt you for an administrator password when it is needed.|

### Stage 5

### Stage 6

| 排名 | 指令 | 說明 |
| -------- | -------- | -------- |
| 1 | del | 刪除一個或多個檔案。 此命令會執行與 清除 命令相同的動作。Del 命令也可以使用不同的參數，從 Windows 修復主控台執行。|
|2|taskkill|結束一個或多個工作或處理序。 處理序可以依處理序識別碼或映像名稱結束。 您可以使用 [ tasklist 命令 ] 命令來判斷處理序識別碼 (PID) ，以便結束進程。|
|3|klist|Displays a list of currently cached Kerberos tickets. This information applies to Windows Server 2012.|
|4|wevtutil|可讓您擷取事件記錄檔和發行者的相關資訊。 您也可以使用此命令來安裝和解除安裝事件資訊清單、執行查詢以及匯出、封存和清除記錄檔。|
|5|rd|刪除目錄。Rd 命令也可以使用不同的參數，從 Windows 修復主控台執行。|

## JPCERT工具分析
==已驗證的工具清單==
| 用途 | 工具 |
| -------- | -------- |
|Command execution | PsExec |
||wmic|
||schtasks|
||wmiexec.vbs|
||BeginX|
||WinRM|
||WinRS|
||BITS|
|Enter password and hash|PWDump7|
||PWDumpX|
||Quarks PwDump|
||Mimikatz (Password hash input lsadump :: sam)|
||Mimikatz (Password hash input sekurlsa :: logonpasswords)|
||Mimikatz (Ticket entry sekurlsa :: tickets)
||WCE|
||gsecdump|
||lslsass|
||Find-GPOPasswords.ps1|
||AceHash|
||Get-GPPPassword (PowerSploit)|
||Invoke-Mimikatz (PowerSploit)|
||Out-Minidump (PowerSploit)|
||PowerMemory (RWMC Tool)|
||WebBrowserPassView|
|Unauthorized relay of communication|Htran|
||Fake WPAD|
|Remote login|RDP|
|Pass-the-Hash Pass-the-Ticket|WCE(RemoteLogin)|
||Mimikatz(RemoteLogin)|
|Privilege escalation|MS14-058 Exploit|
||MS15-078 Exploit|
||SDB UAC Bypass|
|Stealing domain administrator account|MS14-068 Exploit|
||Golden Ticket (Mimikatz)|
||Silver Ticket (Mimikatz)|
|Add / Remove Local User Groups|net user|
|File sharing|net use|
|Removal of traces|sdelete|
||timestomp|
||klist purge|
||wevtutil|
|Get account information|ntdsutil|
||vssadmin|
||csvde|
||dcdiag|
||nltest|
||nmap|
||ldifde|
||dsquery|

## 四大記錄檔
 - [Sysmon](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon)
 - [事件識別碼](https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/default.aspx)
