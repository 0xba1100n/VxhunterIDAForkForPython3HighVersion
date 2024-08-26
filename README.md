IDA插件，用于vxworks5、6符号表恢复<br>
由于python3.6以上版本的一些语法规则的改变（比如，str和bytes的拼接变得不再是那么“弱类型”等一些问题），且项目多年没有维护，<br>
![b8509bee55f68a9ae6eeafaebbca327a](https://github.com/user-attachments/assets/0a74e103-ba66-47e7-a2ef-0088745102c4)
<br>故Vxhunter基于python3的IDA插件用不了，执行起来会有诸如" TypeError: a bytes-like object is required,not 'str' "之类的报错，所以把修复bug后的插件放这了<br>
常见情况的用法：<br>
1.直接将这两个.py脚本放入ida plugin文件夹下<br>
2.binwalk -Me后，使用grep -r bzero，或者别的函数，找到已经分离的vxworks固件的符号表文件<br>
3.寻找vxworks的主程序，一般binwalk结果里面开头的、size大到反常的那个就是了，并使用IDA打开，要指定好正确的架构和大小端序<br>
4.等待ida分析完成后，然后Edit->Vxhunter->Load Vxworks Symbol File，选定符号表文件，即可开始恢复<br>
![image](https://github.com/user-attachments/assets/2e6337d9-91cd-4852-b15f-3f4cc48b7769)<br>
测试环境：IDA7.5、IDA8.3,基于python3.8<br>
原项目见https://github.com/PAGalaxyLab/vxhunter<br>已停止维护，就不提交修改了<br>
