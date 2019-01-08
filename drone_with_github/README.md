# Drone-Github

建立一個綁定GitHub的Drone

# 需要的軟體
  - Docker
  - docker-compose（版本自己決定，目前在yml中的version有用過2/2.2/3.3）

# 需要的資料
  - 去申請個GitHub account
  - 然後去申請個自己的Github App
  - GitHub app會給一份 CLIENT ID & GITHUB SECRET
  - 然後在ＡＰＰ中設定你的Drone的網站與認證的Callback link
  - 接著找個正常的Linux機器，或是在雲端開個ＶＭ之類的(最好有Public IP)，用來放Drone的

# 在docker-compose中需要填的資料
  - ${DRONE_HOST}: 你的Drone host, 開你的WebGUI用
  - ${DRONE_GITHUB_CLIENT}: 你的Git app client id
  - ${DRONE_GITHUB_SECRET}: 你的Git app secret
  - ${DRONE_SECRET}: 給你的測試Client用的secret

# 執行
  - docker-compose up

# 自動測試流程
  - 打開你的Drone Web後認證
  - 選擇你要被Drone測試的Repo
  - 接著在上述的Repo根目錄加入 .drone.yml
  - 把你的測試行為寫在 .drone.yml
  - 然後push到GitHub
  - 回到你的Drone Web ui你就會看他在跑了（push到github後，它會把自動測試的要求丟到你在Git app上面填寫的web site那，那邊就是你的Drone）
