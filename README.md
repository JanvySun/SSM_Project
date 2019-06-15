# DailyFresh(天天生鲜)
天天生鲜是Python中Django框架的一个经典案例，现将其用java的SSM框架实现

## 版本信息

### v1.1 完成注册功能  
**实现功能：**
- 用户注册：前台校验，成功后发送ajax请求，控制器响应并向数据库表中添加数据
- 用户激活：通过产生唯一激活码查询用户并修改用户激活状态

**暂时发现的问题：**
- 密码明文存储
- 邮件功能未完成
- 异常信息输出在页面上，给人不好的体验
- 用户名和密码存储出现错误(Controller中的json解析出现问题)，存储到数据库的格式为`'"DATA"'`，导致查询出现问题

### v1.2 完成登录功能
**实现功能：**
- 用户登录：通过用户名和密码查询用户并判断用户是否激活，登录成功后将用户存储在session中
- 退出登录：将存储在session中的用户信息清除
- 记住用户名：判断用户是否勾选`记住用户名`，将信息存在cookie中
- 主页顶部显示用户欢迎信息：通过判断session中是否有用户来显示欢迎信息
- **解决json解析问题**
- **500及以上的服务器异常会显示`error.jsp`页面，异常信息通过控制台输出**

**待解决问题：**
- 密码明文存储
- 邮件功能未完成
- 400及以上错误输出在页面上

### v1.3 用户中心
**实现功能：**
- 用户个人信息页面：查询用户基本信息显示在页面上
- 用户地址页面：查询用户默认收获地址显示在页面上
- 添加地址：向用户表对应的地址表中添加地址
- 拦截器：用户需要登录才能访问用户中心页面，设置一个跳转参数，用户登录后可直接跳转到被拦截的页面
- 页面抽取：将信息页面(error.jsp,registerOK.jsp,active.jsp)合并为一个(info.jsp)

**待解决问题：与上一个版本相同**

### v1.4 后台管理(用户及其地址)
**实现功能：**
- 用户信息CRUD：查询所有用户并分页显示；增加用户；修改用户信息；删除用户(删除所有选中的用户)
- 地址信息CRUD：通过用户ID查询其地址显示；增加地址；修改地址；删除记录

**暂时未解决：**
- 管理员登录
- 管理页面拦截器
- **上版本遗留问题**

### v1.5 后台管理基本完成
**实现功能：**
- 商品类型查询与修改：商品类型为固定内容，只能修改其图片url
- 商品SPU查询
- 商品SKU查询与修改
- 首页轮播图的CRUD
- 管理员首页
- **管理员登录**：包含验证码的校验
- **管理页面拦截器**

**暂未解决问题：**
- 密码明文存储
- 邮件功能未完成
- 400及以上错误输出在页面上

### v1.6 商品页面
**实现功能：**
- 首页：通过查询数据库显示内容
- 购物车数量：redis数据库存储用户购物车信息，可查询其商品种类数目进行显示
- 商品详情页面
- 商品列表页面
- 商品查询：通过模糊查询显示查询到的商品
- 商品添加购物车：购物车控制器响应

**暂未解决：上版本遗留问题**
