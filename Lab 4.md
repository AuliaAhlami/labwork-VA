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

![image alt](https://github.com/AuliaAhlami/labwork-VA/blob/1aa1b433275994596af546f50502f72a13bf2998/image/Screenshot%202026-04-13%20152441.png)

As far as we are aware, Dog has a Zip archived file.JPG. Then, we can now extract it by using:

    binwalk -e dog.jpg
    ls
A directory called _dog.jpg.extracted was created when the hidden archive was extracted. I then used ls to modify the directory to _dog.jpg.extracted so I could see what was within.

    cd _dog.jpg.extracted
    ls
I discovered a file called hidden_text.txt within and opened it to see what was inside.
    
    open hidden_text.txt
![image alt](https://github.com/AuliaAhlami/labwork-VA/blob/df3607c12664301da4ac6c02737e486c42684ca5/image/Screenshot%202026-04-13%20151015.png)

The string "THIS IS A HIDDEN FLAG" was then discovered.

5.0 FILES

    file solitaire.exe
    file rubiks.jpg
Regardless of their extensions, I was able to determine true nature of files using the file command.

![image alt](https://github.com/AuliaAhlami/labwork-VA/blob/bea44fe427e2d6f53e0b1285dea0c52548142410/image/Screenshot%202026-04-13%20153325.png)

As we can see here, solitaire.exe turns out to be .png extension. Then, we have to change the file's extension to .png and open it.

    mv solitaire.exe solitaire.png
    open solitaire.png
![image alt](https://github.com/AuliaAhlami/labwork-VA/blob/70c14fab0a2937b0e7dd40bc8d350e66c872d320/image/Screenshot%202026-04-13%20153011.png)

The solitaire image can now be opened.

The same applies to rubiks.jpg.

![image alt](https://github.com/AuliaAhlami/labwork-VA/blob/9f7c4f6b515cd6d44741c68c44bebee4d2de186a/image/Screenshot%202026-04-13%20153350.png)

Rubiks.jpg is actually a.png extension, as we can see here. Once more, we must open the file after changing its extension to.png.

    mv rubiks.jpg rubiks.png
    open rubiks.png
![image alt](https://github.com/AuliaAhlami/labwork-VA/blob/862f48278da79b3639bfd319bd47c191cd17dcfb/image/Screenshot%202026-04-13%20153247.png)

    We may now access the Rubik's image.
