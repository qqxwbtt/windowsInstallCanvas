#            windows install canvas

+ windows下安装canvas模块安装了半天，记录下来以便下次再用
  1. 先安装 Python;  通过Python 官网 http://www.python.org/getit/ 下载并安装最新版本.  然后将Python 的安装目录(如: C:\Program Files\Python) 添加到PATH环境变量中;

  2. 安装node-gyp 或将 npm 升级到内含 node-gyp 的版本  (nodejs v0.6.13以上的 npm 已内置了node-gyp, 则此步可以略过);

  3. 再安装 Visual C++ 2010 Express; 因为需要用到其中的MSBuild 用以编译 cairo 类库到本地代码; 微软官方获取: http://www.microsoft.com/visualstudio/en-us/products/2010-editions/visual-cpp-express  (VC++下载和安装的过程很漫长,需要耐心等待);

  4. 还要下载包含 cairo 图形处理库的GTK包: http://ftp.gnome.org/pub/gnome/binaries/win32/gtk+/2.24/gtk±bundle_2.24.10-20120208_win32.zip  ***选择给定本版本！！！！！！！！ 就是因为这个原因搞了半天***
  ~~http://cairographics.org/download/ , 选gtk±bundle_2.24.10-20120208_win32 或最新版~~,

  5. 将下载的GTK包解压到 C:\GTK\ 目录(必须是这个目录名,否则接下来的MSBuild编译可能通不过),

  6. 在Windows环境变量PATH  后添加 C:\GTK\bin 目录 (需要注销Windows重新登录才能全局生效),    以供 canvas 运行时调用cairo的动态链接库 libcairo-2.dll 等;

  7. 最后 npm install canvas , 期间将自动运行MsBuild 编译生成 canvas.node 本地目标库,生成的目标库位于 path\to\node_modules\canvas\build\Release\canvas.node;


+ 参考地址
  https://cnodejs.org/topic/505080cb5aa28e09430d89b0