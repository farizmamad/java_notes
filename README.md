# PERSONAL NOTE ABOUT JAVA
## A. Object-Oriented Programming
Java pada dasarnya merupakan bahasa pemrograman berbasis object. Setiap program dalam Java ditulis dalam class. Oleh karena itu, penting untuk memiliki pemahaman mengenai Object-Oriented Programming jika ingin menulis program dengan Java. Pemahaman ini juga berguna apabila bekerja dengan bahasa pemgrograman lain yang bisa digunakan untuk Object-Oriented Programming.

### A.1. Fundamental
Object-Oriented Programming secara ekstensif menggunakan object sebagai program yang dijalankan dan class sebagai tempat program ditulis. Object merupakan instansiasi dari class, alias object adalah hasil realisasi dari class. Setiap class memiliki parameter (atribut) dan method (perilaku). Perlu dicatat bahwa setiap object hasil intansiasi dari class memiliki nilai atribut yang berbeda dari object lain hasil instansiasi class yang sama, karena nilai atribut dimiliki oleh masing-masing object, bukan class.

Ada 4 prinsip yang mendasari Object-Oriented Programming, yaitu:
<ol>
  <li>Abstraction : adanya class menjadikan inti program yang bersifat low-level dibungkus oleh atribut atau method yang bersifat high-level. Dengan begitu, pengguna akan melihat definisi high-level yang mudah dipahami saja, tanpa perlu mengetahui definisi low-level nya </li>
  <li>Encapsulation : </li>
  <li>Inheritance : antara dua class bisa terbentuk hubungan parent-children, di mana  class children mewarisi atribut dan method dari class parent. Andaikata class children punya detil atribut atau method yang berbeda dari class parent, child bisa meng-override atribut dan method dari parent</li>
  <li>Polymorphism : banyak class bisa berbeda-beda implementasinya, walaupun memiliki atribut dan method yang serupa</li>
</ol>


## B. Multi-threading
Multi-threading adalah salah satu fitur dalam Java yang memungkinkan dua atau lebih thread berjalan secara bersamaan, terutama pada komputer multi CPU. Multi-threading berguna untuk meningkatkan efisiensi waktu komputasi, terlebih lagi saat ada beberapa komputasi yang tidak saling terhubung dalam suatu proses. Istilah lain dari multi-threading adalah <i>lightweight process</i>.

### B.1. Fundamental
Thread bisa berada dalam 1 dari 5 state: New/Create, Starting, Running, Waiting, Dead. 
<ol>
  <li> New/Create : Instansiasi thread dari kelas </li>
  <li> Starting : Menjalankan thread dan menyematkan program yang ingin dijalankan di dalamnya </li>
  <li> Running : Menjalankan program di dalam thread </li>
  <li> Waiting : Program dalam kondisi sleep </li>
  <li> Dead : Thread dimatikan </li>
</ol>

### B.2. Cara Membuat Program Multi-threading dalam Java
<ol>
  <li>Implementasi interface <b>Runnable</b>
    <ol>
      <li>override method <b>run()</b>. Isi dengan program yang ingin dijalankan</li>
      <li>override method <b>start()</b>. Catatan: method ini sudah memanggil method run() secara otomatis tanpa perlu kita tulis dalam method start()</li>
    </ol>
  </li>
  <li>Inherit class <b>Thread</b>
    <ol>
      <li>override method <b>run()</b>. Isi dengan program yang ingin dijalankan</li>
      <li>override method <b>start()</b>. Catatan: method ini sudah memanggil method run() secara otomatis tanpa perlu kita tulis dalam method start()</li>
    </ol>
  </li>
</ol>

Implementasi interface <b>Runnable</b>
<pre>
class ThreadDemo implements Runnable{
  private Thread t;
  private String threadName;
  
  ThreadDemo(String name){
    threadName = name;
    System.out.println("Creating " + threadName + "...");
  }
  
  public void start(){
    System.out.println("Starting " + threadName + "...");
    if(t==null){
      t = new Thread(this, threadName);
      t.start();
    }
  }
  
  public void run(){
    System.out.println("Running " + threadName + "...");
    // write main activity of this class here
    System.out.println("Stopping " + threadName + "...");
  }
}
</pre>



Inherit class <b>Thread</b>
<pre>
class ThreadDemo extends Thread{
  private Thread t;
  private String threadName;
  
  ThreadDemo(String name){
    threadName = name;
    System.out.println("Creating " + threadName + "...");
  }
  
  public void start(){
    System.out.println("Starting " + threadName + "...");
    if(t==null){
      t = new Thread(this, threadName);
      t.start();
    }
  }
  
  public void run(){
    System.out.println("Running " + threadName + "...");
    // write main activity of this class here
    System.out.println("Stopping " + threadName + "...");
  }
}
</pre>
