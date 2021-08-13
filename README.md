# iTMSUpload
该脚本功能，本地化自动上传AppStore的品相，
应用场景：譬如你要上传200到不等的品相到商店，你是选择手动上传呢？还是自动化脚本上传呢？

相关文档地址：
https://help.apple.com/itc/transporteruserguide/#/apdATD1E1958-D1E1A1303-D1E1958A1126

注意事项：
保证 iTMSTransporter 命令工具与要上传的文件在同一个目录下，否则iTMSTransporter会报出路径错误的问题。

准备工作：
1、新建上传的配置文件：
在工具同一层目录下新建upload目录，并在upload中添加三个文件Excel.xlsx、images、onlyOne.png

Excel.xlsx  -  该文档是由osa中定义的品相信息格式而导出的文件。
images  -  该目录是对应品相的用于上传的审核图,每个图片名称由特殊品相id来命名，多个时用 下划线_ 来拼接
onlyOne.png   -  该文件是用于品相的上传的审核图，只有当该品相没有对应的images文件时，会成为替代文件

iTMSTransporter命令行工具路径：
/Users/xuzhenwen/Documents/许多蚊/Job/aIT_lifeStyle/Python_XZW/03iOS自动化/Transporter/iTMSTransporter/itms/bin/iTMSTransporter 
iTMSTransporter is copied from Transporter.app/Contents/itms

运行：
xuzhenwendeMacBook-Pro:bin xuzhenwen$ iTMSUpload

usage: iTMSUpload [-h] -a ACCOUNT -t TEAMID -c CIPHER -s SKU -i IMAGES -e EXCEL

*这是一个本地上传品相的工具*

optional arguments:
  -h, --help            show this help message and exit
  -a ACCOUNT, --account ACCOUNT
                        Select an apple account
  -t TEAMID, --teamid TEAMID
                        Enter the teamid for your apple account
  -c CIPHER, --cipher CIPHER
                        Enter the security password for your apple account
  -s SKU, --sku SKU     Select an app bundleId
  -i IMAGES, --images IMAGES
                        Enter picture directory path
  -e EXCEL, --excel EXCEL
                        Enter Excel.xlsx file path
xuzhenwendeMacBook-Pro:bin xuzhenwen$ iTMSUpload -a xxx -t xxx -c xxx -s xxx -i /Users/xuzhenwen/Documents/许多蚊/Job/aIT_lifeStyle/Python_XZW/03iOS自动化/Transporter/iTMSTransporter/itms/bin/upload/images -e /Users/xuzhenwen/Documents/许多蚊/Job/aIT_lifeStyle/Python_XZW/03iOS自动化/Transporter/iTMSTransporter/itms/bin/upload/Excel.xlsx

结果：
会在脚本同一个目录下生成包名上传文件，比如：/Users/xuzhenwen/Documents/许多蚊/Job/aIT_lifeStyle/Python_XZW/03iOS自动化/Transporter/iTMSTransporter/itms/bin/com.yuyoyuyo.com.xxj/xxj.itmsp

以及仔细查看命令工具执行的情况,以及日志信息，及时反馈问题。
还有成功上传的情况，需要前往商店验证一下情况，大部分是没有问题的。




技术支持与bug反馈的联系方式：QQ 450010152




