____  ___________   ________  ____  ___
\   \/  /\_____  \  \_____  \ \   \/  /
 \     /  /   |   \  /   |   \ \     / 
 /     \ /    |    \/    |    \/     \ 
/___/\  \\_______  /\_______  /___/\  \
      \_/        \/         \/      \_/
:: XOOX :: (V2.0.RELEASE) 数据检索系统
:: 作者 ：wuyou20240101
:: 更新日期：2025.1.23


========================前言=============================
# data-retrieval--
PHP+JS+HTML自己编写的一个社工库（数据检索系统）适用于自己有数据用于存放私有数据，目前功能有文件数据上传以及增删改查，文件支持xlsx、txt、vgs文件上传

========================说明=============================
1、需要至少不低于php7.3.4、MySQL5.7.26的环境
2、内含数据库自己导入你搭建的数据库中即可
3、需要添加/删除字段的需要自己修改根据自己需求来

* 如果实用性热度比较高后续会继续更新

// 上传功能相需求文档--------------------------------------------------------------------------------------------------------开始线------


数据库连接信息："$dbhost="localhost;$dbusername="xooxhennaisi";$dbpassword="xooxhennaisi";$db="xooxhennaisi";$sgk="sgk";"

sgk表中的字段有:"id、姓名、性别、学号、电话、身份证、班级、院系、宿舍床位号、家庭住址、其他信息、备注"

使用语言\函数："php7.3.4、mysqli_*(MySQL5.7.26)、composer2.5.8"

需要上传文件种类：".xlsx/.txt/.vgs"

上传文件提取数据到数据库逻辑："所有字段都可以为空（唯一标识也可以为空），唯一标识梯级为（第一唯一标识是学号，
如果学号不存在则唯一标识是电话，如果电话不存在则唯一标识是身份证），遇到相同学号的数据进行补空的同时判断该库
中这条数据其它的已有字段是否与上传文件中相同，如果相同也没有新字段的数据的话则不需要做任何操作也不需要询问直接跳过该条数据，
如果不同则弹出提示（显示两条数据哪里不同的对比）询问要不要更新库中数据（要更新则把库中的数据替换为刚上传的表中
对应数据，如果不需要更新则进行补空后跳过该条数据继续下一条数据的处理）如果不存在则不需要询问直接插入新纪录数据
，上传文件中的列表头为随机不是按照数据库中列表头的固定顺序，所以需要修改为自动获取上传文件数据中对应列表头下的
数据进行上传"



        '院系' => '院系',
        '性别' => '性别',
        '班级' => '班级',
        '学号' => '学号',
        '姓名' => '姓名',
        '备注' => '备注',
        '其他信息' => '其他信息',
        '身份证' => '身份证',
        '电话' => '电话',
        '宿舍床位号' => '宿舍床位号',
        '家庭住址' => '家庭住址'

// 上传功能相需求文档--------------------------------------------------------------------------------------------------------结束线------






// 单条数据修改功能需求文档--------------------------------------------------------------------------------------------------------开始线



数据库连接信息："$dbhost="localhost;$dbusername="xooxhennaisi";$dbpassword="xooxhennaisi";$db="xooxhennaisi";$sgk="sgk";"

sgk表中的字段有:"id、姓名、性别、学号、电话、身份证、班级、院系、宿舍床位号、家庭住址、其他信息、备注"

使用语言\函数："php7.3.4、mysqli_*(MySQL5.7.26)、composer2.5.8"

修改数据页结构："通过字段的检索找到指定的数据后以个人详细档案表格形式（具体项根据sgk表中的字段）显示在页面上，可以点击修改按钮进行修改，修改完成后点击保存即可把这条修改的数据更新到数据库中"

修改数据页逻辑："点击修改进入编辑模式，编辑完成后点可以点击保存则更新该条数据到服务器，修改成功则弹出提示"修改成功"否则弹出提示"修改失败"，点击修改进入编辑模式后修改，点击取消修改则不做保存并且退出编辑模式"


// 单条数据修改功能需求文档--------------------------------------------------------------------------------------------------------结束线
