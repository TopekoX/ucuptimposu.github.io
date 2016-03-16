---
ads: true
comments: true
date: 2010-01-13 03:02:00+00:00
layout: article
slug: mengubah-text-pada-frame-menjadi-tidak-boldbercetak-tebal
title: Mengubah Text pada Frame menjadi tidak Bold(Bercetak Tebal)
wordpress_id: 301
categories: java
tags: [java, java swing]
---

Defaultnya ketika kita membuat program Java Swing , text pada Frame yang ditampilkan itu defaultnya bercetak tebal atau Bold.
Contoh nya:





![](http://i66.tinypic.com/23iv1jm.jpg)




Coba anda perhatikan teksnya pada label ataupun pada Button nya bercetak tebal!!!! ,,,.Bagaimana kalau kita mau ganti menjadi tidak Bold atau tulisannya biasa aja....???

Gampang anda tinggal menambahkan kode berikut dalam method `main` sebelum kita memanggil objek dari kelas kelas JFrame yang kita buat :

`UIManager.put("swing.boldMetal",Boolean.FALSE);`

Misalnya kita membuat kelas turunan dari `JFrame` dengan misal nama kelasanya `DemoFrame`
contoh:


```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class DemoFrame extends JFrame {

public DemoFrame() {

JLabel label=new JLabel("Salam Topeko..!!!");
JButton tombol=new JButton("Tombol");

tombol.setPreferredSize(new Dimension(200,20));

tombol.addActionListener(new ActionListener(){
public void actionPerformed(ActionEvent evt){
JOptionPane.showMessageDialog(DemoFrame.this,"Topeko Forever"+ "PRIKITIEW...!!!!nwww.topeko.blogspot.com","About",
JOptionPane.INFORMATION_MESSAGE);

}

});

setLayout(new FlowLayout());
getContentPane().add(label,"Center");
getContentPane().add(tombol,"South");
setSize(300,100);
setDefaultCloseOperation(EXIT_ON_CLOSE);
setVisible(true);

}

public static void main(String[] args) {

/*Menonaktifkan text Bold*/
UIManager.put("swing.boldMetal",Boolean.FALSE);

//--------------------------//
SwingUtilities.invokeLater(new Runnable() {
public void run(){
//memanggil objek DemoFrame
new DemoFrame();
}
});

}
}
```




Hasilnya setelah kita jalankan

![](http://i67.tinypic.com/rc3dow.jpg)




Teksnya sudah berubah dari Bold menjadi teks biasa.Efeknya juga tetap sama setiap kita memanggil Window Dialog atau yang Component lainya....


Semoga bermanfaat...
