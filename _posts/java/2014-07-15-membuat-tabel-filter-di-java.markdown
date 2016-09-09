---
comments: true
date: 2014-07-15 16:33:11+00:00
layout: article
slug: membuat-tabel-filter-di-java
title: Membuat Tabel Filter (Penyaringan) data tabel Java Swing
categories: java
tags: [java, swing]
ads: true
image:
  feature:
  teaser: java.jpg
---

Sebelum menggunakan cara ini biasanya saya pake fungsi Search manual dengan query database buat nampilin data yang ingin dicari tapi pas ketemu cara ini. wah ternyata lebih mudah dan fleksibel buat filter data...

![](http://i63.tinypic.com/11ch7v4.jpg)

![](http://i68.tinypic.com/wuqt7q.jpg)

![](http://i66.tinypic.com/6hjcqa.jpg)

![](https://i.imgflip.com/ac1vv.gif)

<center><script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><!-- BOX--><ins class="adsbygoogle"  style="display:inline-block;width:300px;height:250px" data-ad-client="ca-pub-4504493660273886" data-ad-slot="1638134271"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script></center>


``` java
**
 *=========================================================
 * Program ini dibuat oleh Ucup Topeko
 * URL: www.timposu.com
 * email : ucup.timposu@gmail.com
 * Silahkan kode Java ini dipelajari / disebarkan
 * secara bebas...
 *==========================================================
 *

 import java.awt.BorderLayout;
 import javax.swing.JFrame;
 import javax.swing.JScrollPane;
 import javax.swing.JTable;
 import javax.swing.JTextField;
 import javax.swing.RowFilter;
 import javax.swing.SwingUtilities;
 import javax.swing.event.DocumentEvent;
 import javax.swing.event.DocumentListener;
 import javax.swing.table.DefaultTableModel;
 import javax.swing.table.TableRowSorter;
**
*
* @author ucup
*/
public class TableFilter extends JFrame{
private static final long serialVersionUID = 1L;

  private JTextField txtFilter;
  private DefaultTableModel model;
  private JTable table;
  private JScrollPane scrollPane;
  private TableRowSorter sorter;

  public TableFilter() {
    super();
    initComponent();
  }

  private void initComponent() {
    txtFilter = new JTextField();
    table = new JTable();
    //memanggil method tablemodel
    initTableModel();
    //aksi TextField txtFilter
    aksiTxtFilter();
    scrollPane = new JScrollPane();
    scrollPane.setViewportView(table);
    getContentPane().add(txtFilter, BorderLayout.NORTH);
    getContentPane().add(scrollPane, BorderLayout.CENTER);
    pack();
    setSize(500, 400);
    setLocationRelativeTo(null);
    setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
  }
  /**
  * Method ini digunakan untuk mendeklarasikan
  * Table Model dan Isinya
  */
  private void initTableModel() {
    if (model == null){
      model = new DefaultTableModel();
      table.setModel(model);

      //memanggil Method dataModel
      dataModel();
      //set sorter
      table.setRowSorter(getRowSorter());
    }
  }
  /**
  * Method ini digunakan untuk mendeklarasikan
  * isi data Tabel Model
  */
  private void dataModel() {
    model.addColumn("Nama");
    model.addColumn("Negara");

    for (int i=0; i < 50; i++){
      model.addRow(new Object[]{"Suarez","Uruguay"});
      model.addRow(new Object[]{"Messi","Argentina"});
      model.addRow(new Object[]{"Muller","Jerman"});
      model.addRow(new Object[]{"Pirlo","Italia"});
      model.addRow(new Object[]{"Agung Hercules","Indonesia"});
    }
  }
  /**
  * Method ini untuk memfilter data yang ada di dalam tabel
  * method ini intinya.. :D
  * @return
  */
  private TableRowSorter getRowSorter() {
    if (sorter == null){
      sorter = new TableRowSorter(model);
    }
    return sorter;
  }
  /**
  * Mendeklarasikan aksi txtFilter
  */
  private void aksiTxtFilter() {
    txtFilter.getDocument().addDocumentListener(new DocumentListener() {
        @Override
        public void insertUpdate(DocumentEvent e) {
          changedUpdate(e);
        }
        @Override
        public void removeUpdate(DocumentEvent e) {
          changedUpdate(e);
        }
        @Override
        public void changedUpdate(DocumentEvent e) {
          if (txtFilter.getText().length() <= 0){
            getRowSorter().setRowFilter(null);
          } else{
            getRowSorter().setRowFilter(RowFilter.regexFilter(txtFilter.getText()));
          }
        }
      });
  }

  public static void main(String[] args) {
    SwingUtilities.invokeLater(new Runnable() {
    @Override
      public void run() {
        TableFilter tableFilter = new TableFilter();
        tableFilter.setVisible(true);
      }
    });
  }
}
```



Atau bisa juga dengan membuat method yang isinya sbb..


``` java
if (txtFilter.trim().isEmpty()){
 ((TableRowSorter<TableModel>) tabelJabatan.getRowSorter()).setRowFilter(null);
 } else {
 ((TableRowSorter<TableModel>) tabelJabatan.getRowSorter()).setRowFilter(RowFilter.regexFilter(txtFilter.getText()));
 }
```
