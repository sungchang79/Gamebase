## Game > Gamebase > 控制台使用指南 > 会员

查询登录游戏的会员信息。


## Search Member

您可以通过输入用户ID / IdP ID来搜索会员信息。
用户ID(User ID)是Gamebase首次登录时自动发放的用户标识。为了减少同音字符造成的混淆，仅使用“ABCDFGHJKLMNPQRSTWXYZ1346789”字符。
IdP ID是Id Provider提供的ID信息，这意味着Id Provider中的唯一标识符，而不是登录时输入的信息。 因此，如果要按IDP ID项搜索，请在输入搜索信息时注意。

搜索到的用户的详细信息显示在顶部，登录、映射、付款、禁用和游戏时间等历史记录显示在底部的选项卡中。


### Detail Information
![gamebase_member_01_201812](https://static.toastoven.net/prod_gamebase/gamebase_member_01_201812.png)

**User **

- **用户ID** : Gamebase用户ID
- **国家代码(USIM)** : 使用用户终端机中的USIM国家代码进行搜集的结果为失败时，将显示为”ZZ”。如果您想查看代码，请查看底部的**登录历史**。
- **最后登录的时间** : 用户最后登录的时间   
- **参加日期** : 用户最初登录的时间
- **账户状态**
  - **一般** : 一般用户
  - **禁用** : 因滥用等理由被禁用(ban)的用户/通过使用右上端的账户状态更改菜单，并可解除禁用。
  - **退出** : 已退出的用户
- **查询推送附加信息** : 查询游戏用户的推送令牌和标签信息。
![gamebase_member_12_202104](https://static.toastoven.net/prod_gamebase/gamebase_member_12_202104.png)


**Identity Provider **

Gamebase允许多个外部IdP协同工作。换句话说，用户可以通过使用一个用户ID注册Facebook和Google两个IDP来登录。SDK在调用**Login using a specific IdP**或'**Add Mapping** API时注册IdP。

- **IdP** : 外部IdP(guest, Facebook, PAYCO, Google 等)
- **Idp ID** : 外部IdP提供的ID(Facebook no, PAYCO ID等)
- **注册日期** : 用户首次注册IdP的时间

#### 添加映射

可添加查询的游戏用户的IdP信息的功能。
带有要连接的IdP的游戏用户信息仅在**正常**时方可进行添加映射操作。
* 在提供用户的IdP设置栏单击要连接的IdP信息的1号按钮，添加至右侧界面后，单击下方**添加映射**按钮。
* 若添加错误，单击**添加映射**按钮前单击2号按钮，可随时更改为其他IdP。
* 收到提供的游戏用户仅有访客信息时，添加新的IdP信息，原有的访客信息将会丢失，因此应注意。
* 提供用户的IdP信息为1个时，若进行操作，提供用户信息将更改为**丢失**状态，且无法继续使用，因此应提前确认。
##### 提供示例
![gamebase_member_03_201812](https://static.toastoven.net/prod_gamebase/gamebase_member_03_201812.png)

#### 解除映射
多重映射的账户可根据请求解除IdP信息关联。
各账户应至少有1个连接信息，因此仅当有2个以上连接信息时按钮方可激活。
* 单击按钮，如下所示，**解除映射**按钮与连接的IdP信息一起显示。

![gamebase_member_04_201812](https://static.toastoven.net/prod_gamebase/gamebase_member_04_201812.png)

* 单击**解除**按钮，如下所示，确认最终确认窗口及IdP信息。单击**确认**按钮，解除映射。

![image alt](http://static.toastoven.net/prod_gamebase/Operators_Guide/Console_Member_RemoveMapping_2.0.png)

### Login History
![gamebase_member_05_201812](https://static.toastoven.net/prod_gamebase/gamebase_member_05_201812.png)

查看查询用户的登录历史记录。
查询时最初可以查询最近1天，您还可以输入想查询的日期来进行查询。但，仅提供过去3个月（90天）的历史记录。
SDK调用与登录相关的API时会添加历史记录。

- **Login Date** : 用户登录应用程序的时间
- **Login Type** : 用户登录的身份验证类型（IdP Login/Guest等）。括号内的信息是实际使用的IdProvider信息。
- **OS / Ver** : 用户登录的OS（IOS / Android / WebGL等）和OS的版本信息
- **Device model** : 登录应用程序的设备型号名称
- **Device Key** : 登录用户的设备的唯一标识值（Android：Android ID，iOS：IDFV）
- **Device Country Code** : 用户登录时在设备上设置的国家代码
- **USIM Country Code** : 用户登录时在USIM卡上设置的国家代码
- **Telecom** : 用户登录时使用的运营商信息
- **Network** : 用户登录的网络类型(Wi-Fi/3G/LTE等)
- **Language Code** : 用户登录时在终端中设置的语言代码信息
- **Store Code** : 用户下载应用的商店信息
- **Client Version** : 应用下载时的客户端版本信息
- **Gamebase SDK Version** : APP使用的Gamebase SDK版本信息
- **etc** : 登录时使用的除上述项之外的其他信息

### Mapping History
![gamebase_member_06_201812](https://static.toastoven.net/prod_gamebase/gamebase_member_06_201812.png)

查看查询用户的Mapping，解除Mapping的历史记录。可查看的最长日期为三个月（90天）。

* **IdP ID** : 登录IdP时使用的ID信息
* **IdP** : Mapping IdP信息
* **日期** : IdP ID和Gamebase ID Mapping映射操作的时间
* **Type** : Mapping操作的详细信息
  - AAM : 添加Mapping
  - ARM : 删除Mapping
  - AFR : 强制删除Mapping
  - GMG : 创建guest帐户
  - OMG : 创建IdP账户

点击Mapping的IDP历史记录可显示基于IdP映射到Gamebase ID的历史记录。
![gamebase_member_07_201812](https://static.toastoven.net/prod_gamebase/gamebase_member_07_201812.png)

### Purchase History
![gamebase_member_08_201812](https://static.toastoven.net/prod_gamebase/gamebase_member_08_201812.png)
查看查询用户的购买记录。
您可以输入要查看的日期。可查看的最长日期为一个月（30天）。

- **Transaction ID** : 用于区分Gamebase内支付的唯一编号。
- **商店** : 已付款的商店信息
- **道具名称** : 用户在APP内购买的实际item名称
- **价格** : 用户购买的item价格
- **货币** : 用户购买时使用的货币类型
- **消费状态** : 付款项目是否已付款
- **付款状态** : 目前的付款进度
- **Store Reference Key** : 商店发行的付款唯一编号
- **付款日期** : 用户尝试购买或完成购买的时间
- **退还日期** : 用户退还item的时间

### Ban History
![gamebase_member_09_201812](https://static.toastoven.net/prod_gamebase/gamebase_member_09_201812.png)

查看查询用户的停止使用记录。

您可以输入要查看的日期。可查看的最长日期为一个月（30天）。

- **开始日期** : 适用用户禁用的开始时间
- **结束日期** : 解除用户禁用的时间
- **模板** : 添加用户禁用时使用的模板名称
- **原因** : 管理员禁用用户的实际原因信息
- **添加人/添加日期** : 管理员/系统信息、日期、时间
- **解除理由** : 管理员解除禁用时输入的解除原因
- **解除注册者/解除注册日期** : 管理员/系统信息、日期、时间

### Playtime

![gamebase_member_10_201812](https://static.toastoven.net/prod_gamebase/gamebase_member_10_201812.png)
按日期查看被查询用户的游戏时间。
您可以输入要查看的日期，可查看的最长日期为一个月（30天）。

### Withdraw History
![gamebase_member_11_202006](https://static.toastoven.net/prod_gamebase/gamebase_member_11_202006.png)
如果查看的用户为已退出的用户，则显示退出历史。
只在查看已退出或预约退出的用户时显示此菜单，而可在此菜单上查看用户的详细退出明细。 

## Transfer account
只在使用**转移账户**功能时才能使用。[启用转移账户功能](./oper-app/#transfer-account)
可以查询游戏用户的转移账户密钥的发放和验证历史。可以解除被禁用的密钥或重新发放过期的密钥。

![gamebase_member_transferaccount_01_202107.png](https://static.toastoven.net/prod_gamebase/gamebase_member_transferaccount_01_202107.png)
**转移账户发放密钥**

- **ID** : 发给游戏用户的转移账户ID
- **发行日期** : 发放转移账户ID的日期
- **有效日期** : 发放的转移账户ID的到期日期
- **状态** : 发放的转移账户ID的现状态
  - <font color="white" style="background-color:#88C637">正常</font>: 发放的密钥为正常状态。通过使用相关密钥，可转移账户。 
  - <font color="white" style="background-color:#FB8F37">阻止</font>: 发放的密钥为阻止状态。使用发放的密钥无法转移账户。
  - <font color="white" style="background-color:#A1A1A1">过期</font>: 发放的密钥已过期。使用发放的密钥无法转移账户。


**转移账户历史**
可查看发给相关游戏用户的密钥历史。
最近发放的密钥将已被选择，而若选择其他密钥，可查看所选的密钥历史。

### 重新发放转移账户
单击**重新发放**按钮，可重新发放新的转移账户密钥。若重新发放，以前发放的密钥无法继续使用。
![gamebase_member_transferaccount_02_202107.png](https://static.toastoven.net/prod_gamebase/gamebase_member_transferaccount_02_202107.png)

- **重新发放ID和密码** : ID和密码全部重新发放。
- **重新发放密码**：ID仍使用以前发放的ID，仅重新发放密码。

#### 重新发放时的注意事项
- 密码在重新发放时仅显示一次，因此进行重新发放后，请务必另行保存相应信息。
- 若未能保存，无其他找回密码的方法，因此应再次进行重新发放。
- 到期的密钥更新到期日期，但账户状态为正常/阻止时，到期日期不更新。
