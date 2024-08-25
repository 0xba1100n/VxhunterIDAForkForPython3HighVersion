IDA插件，用于vxworks5、6符号表恢复<br>
由于python3.6以上版本的一些语法规则的改变（比如，str和bytes的拼接变得不再是那么“弱类型”等一些问题），且项目多年没有维护，<br>
故Vxhunter基于python3的IDA插件用不了，将脚本的bug修复，放在这里备份自用<br>
用法：<br>
1.直接将这两个.py脚本放入ida plugin文件夹下<br>
2.binwalk -Me后，使用grep -r bzero，或者别的函数，找到已经分离的vxworks固件的符号表文件<br>
3.寻找vxworks的主程序，一般binwalk结果里面开头的、size大到反常的那个就是了，并使用IDA打开，要指定好正确的架构和大小端序<br>
4.等待ida分析完成后，然后Edit->Vxhunter->Load Vxworks Symbol File，选定符号表文件，即可开始恢复<br>
![image](https://github.com/user-attachments/assets/9dbc2be8-0caf-42a3-8259-a215a1a8d6f9)<br>
测试环境：IDA7.5、IDA8.3,基于python3.8<br>
原项目见https://github.com/PAGalaxyLab/vxhunter，已停止维护，就不提交修改了<br>
