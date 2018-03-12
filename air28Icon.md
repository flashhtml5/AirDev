*升级到air27/air28后,由于使用的是ios11,打包时图标需要增加一个Assets.car文件,这里记录一下过程:

1,打开链接 http://www.applicationloader.net/appuploader/icontool.php


2,上传一个1024x1024的图标,然后会自动下载一个压缩包*

3,解压后可以看到ios文件夹里有一个Assets.car文件,复制到项目的src文件夹内,并且刷新(清理)项目

4,注意为了保持兼容性,-app.xml里的icons内容不要修改,原有的icon文件也还要保留

5,打包完成后在ios11的手机上可以看到图标则表示正常!
