---
layout: post
title: encode decode
date: 2014-04-05 15:19:22
categories: web
tags: servlet encode Java
comments_gitment: true
---

* TOC
{:toc}

~~~java
public class HttpPrint {
    private ServerSocket serverSocket;

    public HttpPrint() throws IOException {
        serverSocket = new ServerSocket(8080);
    }

    public void show() throws IOException{
        while(true){
            Socket socket = serverSocket.accept();
            byte[] buf = new byte[1024];
            InputStream is =  socket.getInputStream();
            ByteArrayOutputStream os = new ByteArrayOutputStream();
            int n = 0;
            while ((n = is.read(buf)) > -1){
                os.write(buf,0,n);
            }
            os.close();
            is.close();
            socket.close();
            System.out.println(os);
        }
    }

    public static void main(String[] args) throws IOException {
        new HttpPrint().show();
    }
}

# get

![get][get]

# post

![post][post]

![encodeURI][encodeURI]

[get]: {{"/assets/res/logo.png" | prepend: site.imgrepo }}
[post]: {{"/servlet-encode/post.png" | prepend: site.imgrepo }}
[encodeURI]: {{"/servlet-encode/encodeURI.png" | prepend: site.imgrepo }}
[encodeURI-link]: http://www.w3school.com.cn/jsref/jsref_encodeuri.asp