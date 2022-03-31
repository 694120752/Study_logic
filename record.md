1.Project  包含了项目的所有信息
2.Target   对某些代码的具体构建方式
3.Scheme   配置编译对象（buildSetting里的选项release还是debug）
 
### 多target
1. 多环境可以用多target（右击当前的 然后 选Duplicate）联编
2. 复制后修改info.plist  修改完之后要在BuildSetting中 搜索info路径（Info.plist File）
3. buildSetting 搜 mac （Apple Clang - Preprocessing -> Preprocessor Macros  自定义Debug下变量 DEV=1 然后Release 下DEV=0）
使用时
、、、 objective-c
#if DEV
#endif
、、、
Swift搜 Other Swift Flags

##### 缺点
* 多个info
* 配置比较繁琐

#### 删除
* 右击target删除
* 对应的inf.plist 手动删除
* Edit Scheme -> Manage Schemes 选中对应的 删掉

### 多Scheme
~~1. 选中Project info 中 Configurations 小+号~~
1. Manage Schemes 点+ 
2. 找到对应的Target 自己起名字
3. 选中对应的scheme 对应刚刚准备工作的 Configurations

#### 多Sheme使用示例
* 选中Target Build Setting 直接点+号 (Add User-Defind Setting)
* 随便起个名字 URL 创建的三个Scheme会自动生成
* Info.plist里 增加一个String字段 对应的值为 ${URL}
* 代码中直接读取plist文件 取出来的值就不一样了