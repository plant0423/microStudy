### 数据表

- userInfo

  - email
  - userName
  - sex
  - address
  - tel
  - birth
  - isAdmin
  - depositAmount 押金/余额
  - membershipLevelID 用户等级

- membershipLevels 会员等级

  - levelID

  - discountRate 折扣率

  - 当前等级 (CurrentLevel)：规定升级前的会员等级。

  - 目标等级 (TargetLevel)：规定升级后的会员等级。

  - 升级条件 (UpgradeCondition)：定义用户需要满足的升级条件，例如积分、消费金额等。

  - | levelID | CurrentLevel | TargetLevel | UpgradeCondition | discountRate | ExpirationDate |
    | ------- | ------------ | ----------- | ---------------- | ------------ | -------------- |
    | 1       | Basic        | Silver      | 10次             | 2023-01-01   | 2023-12-31     |
    | 2       | Silver       | Gold        | 50次             | 2023-01-01   | 2023-12-31     |
    | 3       | Gold         | Platinum    | 100次            | 2023-01-01   | 2023-12-31     |

- userDetail

  - email
  - level
  - balance 余额
  - coupon 优惠券	

- bookInfo

  - bookID
  - bookName
  - author
  - ISBN
  - publishDate
  - publishHouse
  - totalCount
  - availableCount 可借库存
  - tag
    - []
  - createTime
  - updateTime
  - picture

- bookReview

  - reviewID
  - bookID
  - reviewLevel(*)
    - 0(default)
    - 1
    - 2
    - 3
    - 4
    - 5
  - reviewDetail(option)

- orderInfo
  - orderID
  - email
  - bookID
  - borrowDate 借书日期
  - reservationDate  预约日期
  - dueDate 应还日期
  - returnDate 实际还书日期
  - delayCount 延期次数
  - isReturned  0 1 2
  - isBorrowOrder 标记为 true 表示借书订单，标记为 false 表示预约订单
  - cancellationDate 如果用户取消了预约，则记录取消日期
  - isReview

- hisOrderInfo
  - orderID
  - email
  - bookID
  - orderType 标记为 "借书" 或 "预约"，以区分不同类型的订单
  - borrowDate
  - ReservationDate
  - dueDate
  - returnDate
  - isDelay
  - isReview
  - isReturn
- expectBook
  - bookID
  - bookName
  - author
  - ISBN
  - publishDate
  - publishHouse
- **图书馆事件日志表 (LibraryLogs)**：存储系统事件和日志信息，例如管理员操作记录、异常情况等。
  - 日志ID (LogID)
  - 用户ID (UserID)
  - isadmin
  - 事件类型 (EventType)
    - 管理员事件
      - 补库
      - 修改
      - 退库
      - 人员管理
      - 审核~~~~
    - 借
    - 还
    - 买
    - 充
    - 退
  - 事件描述 (EventDescription)
  - 时间戳 (Timestamp)