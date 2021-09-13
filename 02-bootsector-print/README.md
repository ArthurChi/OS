# TTY模式
> https://www.cnblogs.com/sparkdev/p/11460821.html

# 本节具体功能解释
https://zoxoy.club/post/Print-char-by-INT-0x10/
在这篇文章中解释的已经非常清晰了

> 屏幕输出</br>
BIOS中断INT 0x10有很多不同的功能，各个功能的入口是通过CPU寄存器AH的值来决定的，比如在Teletype模式下显示字符的功能号就是0E。</br>
</br>
功能号：0EH</br>
</br>
功能：在Teletype模式下显示字符</br>
</br>
入口参数：</br>
</br>
AH＝0EH</br>
AL＝字符</br>
BH＝页码</br>
BL＝前景色(图形模式)</br>
出口参数： 无</br>
</br>
使用方法：</br>
</br>
使用移位mov指令将16进制数0x0E移至CPU寄存器AH上，将要显示的字符移至CPU寄存器AL上，然后再通过int 0x10触发中断输出至屏幕。</br>