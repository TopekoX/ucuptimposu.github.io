---
author: ucup
comments: true
date: 2010-03-13 07:42:00+00:00
layout: article
slug: membuat-progressbar-dengan-java
title: Membuat ProgressBar dengan Java
wordpress_id: 298
categories:
- Java

tags:
- Java
- Java Swing
- Java GUI
---

Salah satu pendekatan yang dapat di lakukan untuk membuat progressbar(JProgressBar) adalah dengan membuat kelas turunan dari objek SwingWorker.Kelas turunan yang kita buat kemudian mengoverride method doInBackground() , dan done().

![](http://i64.tinypic.com/2pta4h1.jpg)

Berikut ini contoh kode program yang nantinya dapat anda kembangkan sendiri.......



    import com.sun.java.swing.plaf.nimbus.NimbusLookAndFeel;

    import java.awt.Dimension;

    import java.awt.GridLayout;

    import java.util.logging.Level;

    import java.util.logging.Logger;

    import javax.swing.JFrame;

    import javax.swing.JLabel;

    import javax.swing.JOptionPane;

    import javax.swing.JProgressBar;

    import javax.swing.SwingUtilities;

    import javax.swing.SwingWorker;

    import javax.swing.UIManager;

    import javax.swing.UnsupportedLookAndFeelException;

    public class DemoProgressBar extends JFrame {

    JProgressBar progressBar;

    JLabel status;
    public DemoProgressBar() {

    //menentukan nilai awal dan nilai akhir

    progressBar=new JProgressBar(0, 100);

    //menentukan ukuran progress bar

    progressBar.setSize(new Dimension(400, 30));

    //progressBar.setStringPainted(true);

    status=new JLabel("Status ");
    //membuat Loading

    Task task=new Task();

    task.execute();

    setSize(400, 100);

    setLayout(new GridLayout(2, 1));

    getContentPane().add(status);

    getContentPane().add(progressBar);

    setDefaultCloseOperation(EXIT_ON_CLOSE);

    setLocationRelativeTo(null);

    setVisible(true);

    }

    public static void main(String[] args){

    try {

    UIManager.setLookAndFeel(new NimbusLookAndFeel());

    } catch (UnsupportedLookAndFeelException ex) {

    Logger.getLogger(DemoProgressBar.class.getName()).log(Level.SEVERE, null, ex);

    }
    SwingUtilities.invokeLater(new Runnable() {
    public void run() {

    new DemoProgressBar();

    }

    });

    }

    class Task extends SwingWorker{
    //Override method doInBackground

    protected Object doInBackground() {

    for(int i=0;i<=100;i++){

    try {

    //membuat thread 50 milidetik agar efek progress kelihatan

    status.setText("Status "+i+"%");

    Thread.sleep(50);

    progressBar.setValue(i);

    } catch (InterruptedException ex) {

    Logger.getLogger(DemoProgressBar.class.getName()).log(Level.SEVERE, null, ex);

    }

    }
    return null;

    }

    //Override method done

    protected void done() {

    JOptionPane.showMessageDialog(null,"Loading Selesai");

    }

    }

    }
