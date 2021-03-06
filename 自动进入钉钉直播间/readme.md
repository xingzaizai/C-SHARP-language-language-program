软件的思路：

打开软件-读取主窗口配置文件（没有则跳到打开钉钉一步）- 判断直播时间距离当前时间（未打开自动打开下一次直播则跳到打开钉钉一步）- 显示距离当前直播时间还有xx时xx分xx秒 - 循环等待到达直播开启时间 - 在距离钉钉直播还有xx分钟时打开钉钉 - 打开钉钉 - 将钉钉窗口移动到指定坐标（默认为0，0，可自己设置）- 激活窗口 - 每隔xx秒在指定区域截图（通过图片上的RGB或OCR识别关键字 判断直播是否开启） - 将鼠标移动到指定位置 - 模拟鼠标左键按下打开直播 - 保存钉钉窗口坐标 - 每隔xx秒在指定区域截图判断直播是否中断 -  如果RGB不是直播时的 RGB或者OCR未识别到关键字 则识别为直播断开 - 每隔xx秒钟在指定区域截图判断直播是否恢复 - 超过xx分钟还未检测到直播开启则放弃。（如果在判断直播是否开启的时间内到达了下一场直播的开启时间，则放弃检测并打开下一场直播。）

说白了就是将钉钉窗口移到屏幕左上角，然后在钉钉窗口左上角”XX群 正在直播“处截个图，判断图片中的 RGB是否与直播时的RGB一致 或者 OCR识别图片判断关键字，如果一致则模拟左键点击截图区域就打开直播了。


软件界面介绍：

1、主界面

![图片](https://uploader.shimo.im/f/qZhpuHeif4QTA2gi.png!thumbnail)

![图片](https://uploader.shimo.im/f/vYrliboQ8C5PEdl8.png!thumbnail)

          

2、自定义截图界面

![图片](https://uploader.shimo.im/f/WDbdcXs5Qb0YKGe5.png!thumbnail)                                    ![图片](https://uploader.shimo.im/f/NN8BRrVaCWQsVxUw.png!thumbnail)



软件具体功能说明：

1. 添加自启：

打开此功能后软件将在系统启动后自动启动。

**注意：您需要一定的权限才能使用此功能**

2. 删除自启：

打开此功能后软件将删除已添加的自启动。

**注意：您需要一定的权限才能使用此功能**

1. 自定义截图：

请将自定义截图透明区域移到钉钉窗口左上角”XX群 正在直播“处，然后点击截图，验证成功后退出软件再重新打开。截图成功后将有几率会提高识别钉钉直播是否开启的准确性。

**注意：截图成功后将会保存当前钉钉窗口大小、坐标、截图区域大小、坐标，并且自定义截图需要在钉钉正在直播时进行，才会显示验证成功****。**

2. 删除截图数据：

删除自定义截图将会删除您自定义的截图数据，如果您删除自定义截图前打开并设置过自定义截图区域，那么删除自定义截图数据后将会使截图数据恢复到默认，使用此功能后有可能会降低识别钉钉直播是否开启的准确性。

3. 截图保存到桌面(Debug)：

推荐多次检测直播失败时打开此功能。正常情况下保存到桌面的截图应该和下面这个图差不多，如果多次检测直播失败或者您保存到桌面的截图和下面的截图有差距的话，请点击自定义截图（自定义截图教程在上方），自己设置截图区域。   

  ![图片](https://uploader.shimo.im/f/CBPAUeBLJl83RL56.jpg!thumbnail)

 

 6.阻止系统休眠：

打开此功能会在运行本软件时组织系统休眠

 7.钉钉窗口显示在最前方：

打开此功能后钉钉窗口将显示在屏幕顶层

 8.中断直播时自动进入：

打开此功能后将会打开直播后在每隔（您设定的时间）秒检测一次直播是否中断，如果直播中断，则软件会自动在（您设定的时间）内检测每隔5秒检测一次直播是否恢复。

此功能推荐在网络质量差时打开。

**注意：打开此功能后请不要移动或遮挡钉钉窗口。**

 9.自动开启下一次直播：

如果打开此功能则在当前直播完后将会按照设定并启用的自定义时间自动打开下一场直播，如果未设定或未启用自定义时间或当前时间大于或等于当前已启用的最后一个自定义时间则此功能不会生效。

**注意：打开此功能后请不要移动或遮挡钉钉窗口。**

 10.自定义颜色文件

**此功能有几率****提高（保守点比较好）识别钉钉直播是否开启的准确性。**

1、用取色软件取得钉钉左上角“xx群 正在直播”处任意一个字体的颜色，然后记下那一串十六进制颜色码

![图片](https://uploader.shimo.im/f/6ePCkl7tROD0B2R7.jpg!thumbnail)

2、在自动进入钉钉直播间同一文件夹下新建名为“color.txt”文件

![图片](https://uploader.shimo.im/f/HjMY9zNL5Axxh67j.png!thumbnail)

3、将刚刚那串十六进制颜色码保存到记事本上

![图片](https://uploader.shimo.im/f/2NYH2UwXTIjTNRUY.png!thumbnail)

4、如果有多个颜色码，则每一个颜色码占一行

![图片](https://uploader.shimo.im/f/Mgf8gHVxAurdWiap.png!thumbnail)

11.命令行删除配置文件

如果打开此软件在桌面不显示而只在任务栏显示的话，请使用此功能删除配置文件。

**注意：使用此功能后会删除自定义截图数据和主窗口配置文件，将会导致自定义时间被清除和自定义截图区域失效。**

![图片](https://uploader.shimo.im/f/0kZAIbH5MsyPPFZG.gif)

12.自定义ORC识别关键字

**此功能有几率****提高（同样也是保守点比较好）识别钉钉直播是否开启的准确性。**

1、在本软件目录下新建名为“关键字.txt”的文件

![图片](https://uploader.shimo.im/f/ACaTtM5K6HutMVPq.png!thumbnail)

2、**每行**只能有**一个**关键字

![图片](https://uploader.shimo.im/f/vPleboaaB6I9sgGF.png!thumbnail)

3、保存为UTF-8编码

![图片](https://uploader.shimo.im/f/klQiAyGSmrXMyiKr.png!thumbnail)

4、打开软件测试

13.自定义 OCR识别ApiKey文件

1、在本软件目录下新建名为“apikey.txt”的文件

![图片](https://uploader.shimo.im/f/mEUCqOrT9JL5pLK2!thumbnail)

2、上面一行是：API_KEY，下面一行是：SECRET_KEY

![图片](https://uploader.shimo.im/f/3goTBhZjSa4hJeAx.png!thumbnail)

3、保存为UTF-8编码

![图片](https://uploader.shimo.im/f/klQiAyGSmrXMyiKr.png!thumbnail)

4、打开软件测试


注意事项：

1、运行此软件前请先退出钉钉。

2、打开钉钉后请不要移动或遮挡钉钉窗口，因为截图区域是固定的，移动或遮挡了钉钉窗口那么截图区域就不是钉钉左上角”XX群 正在直播“了，就会造成检测钉钉是否在直播失败。

3、如果多次检测直播失败请点击自定义截图将窗体透明区域移到钉钉窗口左上角”XX群 正在直播“处，然后点击截图，验证成功后退出软件再重新打开。

这个操作就相当于重新设置了截图区域，如果想要恢复默认请点击删除自定义截图。

4、**自定义截图需要在钉钉正在直播时进行，才会显示验证成****功**                 

![图片](https://uploader.shimo.im/f/MXMjFpub1aMqr5KA.png!thumbnail)




**gif教程**

1、使用教程

![图片](https://uploader.shimo.im/f/Z2qy6BrtUiwzy9ne.gif)

2、自定义截图教程

![图片](https://uploader.shimo.im/f/RA81yWEP41oVJeS7.gif) 

更新：

2020-04-29 20:52  此版本出现重大BUG，预计明天修复

2020-04-30 19:08  已修复BUG，但是好像还有些小bug，主功能可以正常使用

2020-05-01 13:19  小bug基本已修复，此软件所有功能均可正常使用

2020-05-01 21:22  在按钮添加提示以及添加黑色主题

2020-05-08 18:48  修复 ：不能打开下一次直播、未到达最后一个自定义时间却显示 “已到达最后一个自定义时间，自动开启下一次直播将不会生效” 等问题

                              添加：运行软件时阻止系统休眠、手动保存主窗口配置文件等功能

                              优化：C#重写读写配置文件DLL，运行新版软件时不需要“ReadOrWriteFile.DLL”

2020-05-09 16:32 添加：1、接入百度文字识别API（通过识别关键字判断直播是否打开）

                                        2、添加自定义OCR关键字文件功能

                                        3、添加判断钉钉直播窗口是否打开功能

                                        4、鼠标左键点击右上角“xx 群正在直播”区域由原来的1次增加到最多30次

2020-05-11 15:15 添加：1、在通用文字识别的基础上添加了通用文字识别（含位置信息版）、通用文字识别（高精度版）、通用文字识别（高精度含位置版），在通用文字识别调用失败时，自动依次调用其他文字识别

                                         2、自定义文字识别ApiKey文件

                                         3、自动更新

                              其它：整合成单文件，新版运行时不需要“Newtonsoft.Json.dll”和“Newtonsoft.Json.xml”

2020-05-14 10:50 修复：更新后造成软件界面不能正常显示

                              其它：打开直播后将会优先检查直播窗口是否关闭（方便全屏观看直播），当检测到直播窗口关闭时，才会检测钉钉窗口左上角的RGB和关键字是否和直播时的RGB和关键字一致

                             注意：此次更新请重新设定自定义截图区域

2020-05-23 10:24 修复：更新软件出错时不能加载配置文件

                             添加：对缩放比为125%、150%屏幕的支持

2020-06-20 19:30 修复：1、自定义截图时显示的图片位置不正确

                                        2、钉钉窗口始终显示最前方无效

                                        3、在高dpi屏幕显示模糊

                              添加：BUG提交入口

                              其它：提高RGB识别的准确性

                              注意：1、此版本为Beta版，可能会有重大BUG

                                        2、此次更新请重新设定自定义截图区域

2020-06-24 20:19 修复：更新后不能自动打开软件和部分BUG

最后修改时间：2020 - 06 - 20

