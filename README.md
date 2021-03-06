S.M.A.R.T. - Static Malware Analysis and Report Tool   
========

feature
--------
- S.M.A.R.T. is a static malicious file analysis tool for Linux, is currently integrating MalwareScan project.
- Expected to include scan module, inspection module, classification module at completion.  
with folder sacn, multi-file scan, PE file analysis, upload suspicious sample and machine-learn classifier.          
- Windows version click [here](http://git.oschina.net/rx_z/mswingui)

--------
reference
--------
- SSMA : [secrary - Simple Static Malware Analyzer](https://github.com/secrary/SSMA)
- ToyMalwareClassification : [bindog - Microsoft Malware Classification](https://github.com/bindog/ToyMalwareClassification)
- malware image : [sarvam project](http://sarvamblog.blogspot.hk/2014/08/supervised-classification-with-k-fold.html)

--------
usage
--------
    git clone https://github.com/zengrx/S.M.A.R.T
    cd S.M.A.R.T
    pip install -r requirements.txt --user (may meet some troubles)
    cd ./src
    python main.py
    python2 main.py (if python's default version is 3.x)

--------
GUI - PyQt4
--------
![main](https://github.com/zengrx/S.M.A.R.T./blob/master/doc/pictures/smart_sacn.png)
![report](https://github.com/zengrx/S.M.A.R.T./blob/master/doc/pictures/smart_report.png)
![history](https://github.com/zengrx/S.M.A.R.T./blob/master/doc/pictures/smart_history.png)
![asm](https://github.com/zengrx/S.M.A.R.T./blob/master/doc/pictures/smart_asm.png)
![detail](https://github.com/zengrx/S.M.A.R.T./blob/master/doc/pictures/smart_detail.png)
![detail2](https://github.com/zengrx/S.M.A.R.T./blob/master/doc/pictures/smart_detail2.png)
![virustotal](https://github.com/zengrx/S.M.A.R.T./blob/master/doc/pictures/smart_vtapi.png)

--------
_(:3 」∠)/
--------
- 在windows中的使用
因为需要使用magic模块，选择32位python2.7版本     
pip install python-magic     
在 http://sourceforge.NET/projects/gnuwin32/files/file/5.03/ 下载 file-5.03-setup.exe     
安装至 C:\GnuWin32     
环境变量Path里添加 C:\GnuWin32\bin      
删除 C:\GnuWin32\share\misc\magic.mgc     
python代码里使用Magic时 指明magic信息文件，否则会报错
      m = Magic(magic_file="C:\GnuWin32\share\misc", mime=False)  
      file_type = m.from_file(file_path)  
- 12月22日更新64位python2.7版本magic模块使用，win7下已验证64位可用

- 需要注意在linux版本与windows版本中编码的不同

- 目前已使用sqlite3为工程数据库，也需要注意编码问题

- 发布版本    
目前使用pyinstaller发布windows64位（PE32+）版本成功
命令为 pyinstaller -w -p path/to/python27; -i path/to/main_icon.ico main.py

- gist特征需要使用快速傅里叶变换库fftw3 
