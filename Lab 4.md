WEEK 4 : METADATA

1.0 EXIFTOOL

    exiftool ocean.jpg
I read the metadata ocean using exiftool.jpg. Metadata can be used to conceal messages, but it also frequently reveals details about the file development.

![image alt](https://github.com/AuliaAhlami/labwork-VA/blob/5e2c5981ed0fa1f6369aa20ff6ad67d5939e6b83/image/Screenshot%202026-04-13%20152126.png)

And I saw the following in the comment: THIS IS HIDDEN FLAG. This demonstrate how photos may have hidden information in metadata sections like comments.

2.0 STRINGS

    strings computer.jpg
I extracted every printable character sequence from the binary file computer.jpg using the strings command.

![image alt](https://github.com/AuliaAhlami/labwork-VA/blob/90648a7e61883ffc2cb370704a70fadf2642cf78/image/Screenshot%202026-04-13%20152149.png)

Standard headers like JFIF and ICC_PROFILE are displayed in the output. In instance, no hidden flags or passwords were discovered. This tool is used as a fast approach to locate flags or passwords hidden in file without using complete hex editor.

3.0 HEXEDITOR

    hexeditor computer.jpg    
I conducted thorough analysis of the computer's binary data using hex editor.JPG.

![image alt](https://github.com/AuliaAhlami/labwork-VA/blob/96b6de71d7ec837bba1f238885f7a32f4cce16f6/image/Screenshot%202026-04-13%20151516.png)

I tried using W to look specific text strings, like "flags," in the raw hex code (seen by the "Text String" search box). The search yielded "** String not found **" in this particular view, indicating that any hidden data in this file may be encoded, encrypted, or include nothing out of the ordinary.

4.0 BINWALK

    binwalk dog.jpg
I looked any hidden or embedded files in dog.jpg using binwalk. The scan found a Zip archive beginning at decimal offset 88221. This tool assist in identifying file signatures that might be stored inside another file.

![image alt](
