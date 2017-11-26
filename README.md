# basis
Describes common statements in Java learning
//文件的输入输出及使用
import java.io.*; 
 //缓冲字符流将键盘输入直接保存到文件中
 
 BufferedReader bufReader = new BufferedReader(new InputStreamReader(System.in)); 
 //从文件中读入子串
 BufferedReader in=new BufferedReader(new FileReader(“input.txt”) )；
 String line=in.readLine();
 //读取一行

//缓冲FileWriter字符输出流
BufferedWriter bufWriter =new BufferedWriter(new FileWriter("Hello.txt")); 
//字节输出流
BufferedInputStream bufferedInputStream =  new BufferedInputStream(new FileInputStream(srcFile)); 

BufferedOutputStream bufferedOutputStream = new BufferedOutputStream(new FileOutputStream(desFile));

FileWriter w = new FileWriter(file,true);
//定义FileWriter 及读写文件
			w.write(number + "号线路：\r\n");
			for(int i = 0;i < site.length;i++)
				w.write(site[i] + " ");
			w.write("\r\n换乘站：" + (change + 1) + ":" + site[change] + "\r\n\r\n");//将换乘站的序号写入文件
			w.close();


//for example

import java.io.*; 
 //缓冲字符流将键盘输入直接保存到文件中
public class BufferedReaderWriterDemo { 
    public static void main(String[] args) { 
        try { 
        	System.out.println("输入文本，键入quit结束");
           // 缓冲System.in输入流
            BufferedReader bufReader = new BufferedReader(new InputStreamReader(System.in)); 
           // 缓冲FileWriter字符输出流
            BufferedWriter bufWriter = new BufferedWriter(new FileWriter("Hello.txt")); 
 
            String input = null; 

           // 每读一行进行一次写入动作
            while(!(input = bufReader.readLine()).equals("quit")) { 
            	//只属于BfferedReader 会把换行符去掉
                bufWriter.write(input); 
                 // newLine()方法写入与操作系统相依的换行字符
                bufWriter.newLine(); 
            } 
 
            bufReader.close(); 
            bufWriter.close(); 
        } 
         
        catch(IOException e) { 
            e.printStackTrace(); 
        } 
    } 
} 


import java.io.*;
 //用缓冲字节复制
public class BufferedStreamDemo {
    public static void main(String[] args) {
        try {
            byte[] data = new byte[1]; 

            File srcFile = new File("BufferedStreamDemo.java"); 
            File desFile = new File("BufferedStreamDemo.java.bak"); 

            BufferedInputStream bufferedInputStream =  new BufferedInputStream(new FileInputStream(srcFile)); 
            BufferedOutputStream bufferedOutputStream = new BufferedOutputStream(new FileOutputStream(desFile));
 
            System.out.println("复制文件：" + 
                             srcFile.length() + "字节");

            while(bufferedInputStream.read(data) != -1) { 
                bufferedOutputStream.write(data); 
            }
            
            // 将缓冲区中的数据全部写出 
            bufferedOutputStream.flush();
 
            // 关闭流 
 
            bufferedInputStream.close(); 
            bufferedOutputStream.close(); 

            System.out.println("复制完成"); 
        } 
        catch(IOException e) { 
            e.printStackTrace(); 
        } 
    }
}
