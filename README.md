# Resource-Sharing-Platform
2C业务应用->资源共享平台


1.业务需求
1.1 立项说明
  本意是打造一款商品代购平台，方便代购者维护并分享商品最新价格等信息。

1.2 业务架构
  1.2.1 商品系统(product system)
    1.2.1.1 商品(product): 
	  名称(name)，编码(number)，唯一标志(id)，描述(description)，生效日期(EFFDT)，失效时间(LEFFDT)，状态(state), 长编码(longNumber),
	  创建日期(createTime)，创建用户(createUser)，最后更新时间(lastUpdateTime)，最后更新用户(lastUpdateUser)，
	  价格(price)，商品类别(category)，品牌(brand)，供应商(vendor)，地址(address)，仅自己可见(isPrivate)，管理员(owner)，
	  
	1.2.1.2 商品分类(category)
	  名称(name)，编码(number)，唯一标志(id)，描述(description)，生效日期(EFFDT)，失效时间(LEFFDT)，状态(state), 长编码(longNumber),
	  创建日期(createTime)，创建用户(createUser)，最后更新时间(lastUpdateTime)，最后更新用户(lastUpdateUser)，
	  上级分类(parent)，是否末级(isLeaf)，仅自己可见(isPrivate)，管理员(owner)，
	
	1.2.1.3 商品族(productFamily)
	  名称(name)，编码(number)，唯一标志(id)，描述(description)，生效日期(EFFDT)，失效时间(LEFFDT)，状态(state), 长编码(longNumber),
	  创建日期(createTime)，创建用户(createUser)，最后更新时间(lastUpdateTime)，最后更新用户(lastUpdateUser)，
	  
	1.2.1.4 价格历史(priceHis)
	  名称(name)，编码(number)，唯一标志(id)，描述(description)，生效日期(EFFDT)，失效时间(LEFFDT)，状态(state), 长编码(longNumber),
	  创建日期(createTime)，创建用户(createUser)，最后更新时间(lastUpdateTime)，最后更新用户(lastUpdateUser)，
	  商品(product)，价格时间(priceTime)，
	  
	1.2.1.5 评价(comment)
	  名称(name)，编码(number)，唯一标志(id)，描述(description)，生效日期(EFFDT)，失效时间(LEFFDT)，状态(state), 长编码(longNumber),
	  创建日期(createTime)，创建用户(createUser)，最后更新时间(lastUpdateTime)，最后更新用户(lastUpdateUser)，
	  用户(user)，商品(product), 内容(content)，评价等级(level)，是否匿名(isAnonymous), 代购人(purchaser)，
	 
	1.2.1.6 关注(like)
	  名称(name)，编码(number)，唯一标志(id)，描述(description)，生效日期(EFFDT)，失效时间(LEFFDT)，状态(state), 长编码(longNumber),
	  创建日期(createTime)，创建用户(createUser)，最后更新时间(lastUpdateTime)，最后更新用户(lastUpdateUser)，
	  用户(user), 商品(product), 关注/屏蔽(isLike),
	  
	1.2.1.7 代购(proxy)
	  名称(name)，编码(number)，唯一标志(id)，描述(description)，生效日期(EFFDT)，失效时间(LEFFDT)，状态(state), 长编码(longNumber),
	  创建日期(createTime)，创建用户(createUser)，最后更新时间(lastUpdateTime)，最后更新用户(lastUpdateUser)，
	  代购人(user), 商品(product), 
	  
  1.2.2 订单系统(order system)
    1.2.2.1 订单头(bill)
	  名称(name)，编码(number)，唯一标志(id)，描述(description)，生效日期(EFFDT)，失效时间(LEFFDT)，状态(state), 长编码(longNumber),
	  创建日期(createTime)，创建用户(createUser)，最后更新时间(lastUpdateTime)，最后更新用户(lastUpdateUser)，
	  用户(user)，
	  
	1.2.2.2 订单分录(entry)
	  名称(name)，编码(number)，唯一标志(id)，描述(description)，生效日期(EFFDT)，失效时间(LEFFDT)，状态(state), 长编码(longNumber),
	  创建日期(createTime)，创建用户(createUser)，最后更新时间(lastUpdateTime)，最后更新用户(lastUpdateUser)，
	  商品(product)，数量(count)，
  
  1.2.3 权限系统(permission system)    主要是限制一些商品的可编辑权限，由于业务特殊性，可以查看所有商品的信息，只限制编辑权限
    1.2.3.1 用户(user)
	  名称(name)，编码(number)，唯一标志(id)，描述(description)，生效日期(EFFDT)，失效时间(LEFFDT)，状态(state), 长编码(longNumber),
	  创建日期(createTime)，创建用户(createUser)，最后更新时间(lastUpdateTime)，最后更新用户(lastUpdateUser)，
	  密码(password)，手机号(telnum)，邮箱(email)，
	
	1.2.3.1 权限分配(user)
	  名称(name)，编码(number)，唯一标志(id)，描述(description)，生效日期(EFFDT)，失效时间(LEFFDT)，状态(state), 长编码(longNumber),
	  创建日期(createTime)，创建用户(createUser)，最后更新时间(lastUpdateTime)，最后更新用户(lastUpdateUser)，
	  用户(user)，商品(product)，
	  
  1.2.4 好友系统(friend system)
    1.2.4.1 好友关系(friendship)
	  名称(name)，编码(number)，唯一标志(id)，描述(description)，生效日期(EFFDT)，失效时间(LEFFDT)，状态(state), 长编码(longNumber),
	  创建日期(createTime)，创建用户(createUser)，最后更新时间(lastUpdateTime)，最后更新用户(lastUpdateUser)，
      用户(user)，好友(friend)，是否接受消息推送(isReceiveMsg),
	  
	1.2.4.1 好友关系(friendship)
	  名称(name)，编码(number)，唯一标志(id)，描述(description)，生效日期(EFFDT)，失效时间(LEFFDT)，状态(state), 长编码(longNumber),
	  创建日期(createTime)，创建用户(createUser)，最后更新时间(lastUpdateTime)，最后更新用户(lastUpdateUser)，
      用户(user)，好友(friend)，是否接受消息推送(isReceiveMsg),
	  
	  
1.3 业务功能
  1.3.1 用户管理
    用户分为普通用户和一个管理员用户，
	1.3.1.1 管理员权限：
	  管理其他用户账号(增删改查，禁用启用)；
	  维护商品族(增删改查，只有管理员可以维护，避免顶级菜单过多过杂)；
	  
	1.3.1.2 普通用户：
	  维护商品分类、商品信息；
	  针对商品发起评论；
	  下订单；
  
  1.3.2 商品管理
    商品可以按照分类查看，顶级为商品族，由管理员用户维护；
	商品族底下可以由普通用户挂多级商品分类，只有末级商品分类可以挂商品；
	每一个商品有一个特定的管理员(owner)，管理员默认为创建该商品的用户，管理员可以分配该商品的编辑权限给其他用户；
	如果商品分类的owner和底下商品的owner不一致，商品分类的owner无法删除该商品分类。
	有编辑权限的用户可以维护该商品的价格历史。
	评论只能由发出评论的用户进行维护。

  1.3.3 订单管理
    用户可以发起订单，选择商品，代购人，

2.系统架构

	  
	
	
	
	






	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	