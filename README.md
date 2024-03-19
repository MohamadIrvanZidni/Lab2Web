# Lab2Web


Saya membuat formulir di mana pengguna diminta untuk memasukkan nama, tanggal lahir, dan pekerjaan mereka. Saya kemudian memproses informasi ini untuk menghitung umur berdasarkan tanggal lahir dan menentukan gaji berdasarkan pekerjaan yang dipilih.

Meminta pengguna untuk memasukkan nama, tanggal lahir, dan pekerjaan melalui form.

Code :
    
    <form method="post">
        <label>Nama: </label>
        <input type="text" name="nama"><br><br>
        <label>Tanggal Lahir (YYYY-MM-DD): </label>
        <input type="date" name="tanggal_lahir"><br><br>
        <label>Pekerjaan: </label>
        <select name="pekerjaan">
            <option value="Programmer">Programmer</option>
            <option value="Designer">Designer</option>
            <option value="Manager">Manager</option>
        </select><br><br>
        <input type="submit" value="Kirim">
    </form>

![Img](Picture/input%20data.png)

Data yang dimasukkan akan diproses untuk menghitung umur berdasarkan tanggal lahir dan menentukan gaji berdasarkan pekerjaan.   

    if (isset($_POST['nama']) && isset($_POST['tanggal_lahir']) && isset($_POST['pekerjaan'])) {
      $nama = $_POST['nama'];
      $tanggal_lahir = $_POST['tanggal_lahir'];
      $pekerjaan = $_POST['pekerjaan'];

      // Menghitung umur
      $tanggal_lahir_obj = new DateTime($tanggal_lahir);
      $sekarang = new DateTime('today');
      $umur = $sekarang->diff($tanggal_lahir_obj)->y;

      // Menentukan gaji berdasarkan pekerjaan
      switch ($pekerjaan) {
         case "Programmer":
            $gaji = 5000000;
            break;
         case "Designer":
            $gaji = 4000000;
            break;
         case "Manager":
            $gaji = 7000000;
            break;
         default:
            $gaji = 0;
      }}

Output dari Data yang telah dimasukkan

    echo "<br><br>";
        echo "Nama: $nama <br>";
        echo "Tanggal Lahir: $tanggal_lahir <br>";
        echo "Umur: $umur tahun <br>";
        echo "Pekerjaan: $pekerjaan <br>";
        echo "Gaji: Rp. $gaji <br>";

![Img](Picture/output%20data.png)
