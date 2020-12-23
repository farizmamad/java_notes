# JAVA
## A. Multi-threading
Multi-threading adalah salah satu fitur dalam Java yang memungkinkan dua atau lebih thread berjalan secara bersamaan, terutama pada komputer multi CPU. Multi-threading berguna untuk meningkatkan efisiensi waktu komputasi, terlebih lagi saat ada beberapa komputasi yang tidak saling terhubung dalam suatu proses. Istilah lain dari multi-threading adalah <i>lightweight process</i>.

### A.1. Fundamental
Thread bisa berada dalam 1 dari 5 state: New/Create, Starting, Running, Waiting, Dead. 
<ol>
  <li> New/Create : Instansiasi thread dari kelas </li>
  <li> Starting : Menjalankan thread dan menyematkan program yang ingin dijalankan di dalamnya </li>
  <li> Running : Menjalankan program di dalam thread </li>
  <li> Waiting : Program dalam kondisi sleep </li>
  <li> Dead : Thread dimatikan </li>
</ol>

### A.2. Cara Membuat Program Multi-threading dalam Java
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
