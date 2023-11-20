# lab7Web
## Pertemuan 9/tugas/rajaheppyanto/312210235

Daftar isi
```
1. Tugas dan pertanyaan
2. Proses praktikum 
```

## 1. Tugas Dan pertanyaan

- Buatlah program PHP sederhana dengan menggunakan form input yang menampilkan
nama, tanggal lahir dan pekerjaan. Kemudian tampilkan outputnya dengan menghitung
umur berdasarkan inputan tanggal lahir. Dan pilihan pekerjaan dengan gaji yang
berbeda-beda sesuai pilihan pekerjaan.

```
code:

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <title>Tugas web pemograman pt 7</title>

    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">
</head>
<body class="container mt-5">
    <h2>Form Input</h2>
    <form method="post">
        <div class="form-group">
            <label for="nama">Nama:</label>
            <input type="text" class="form-control" name="nama" required>
        </div>

        <div class="form-group">
            <label for="tgl_lahir">Tanggal Lahir:</label>
            <input type="date" class="form-control" name="tgl_lahir" required>
        </div>

        <div class="form-group">
            <label for="pekerjaan">Pekerjaan:</label>
            <select class="form-control" name="pekerjaan" required>
                <option value="3D modeling">3D modeling</option>
                <option value="freelancer">freelancer</option>
                <option value="kuli">kuli</option>
            </select>
        </div>

        <button type="submit" class="btn btn-primary">Submit</button>
    </form>

    <?php
    if ($_SERVER["REQUEST_METHOD"] == "POST") {
        $nama = htmlspecialchars($_POST["nama"]);
        $tgl_lahir = htmlspecialchars($_POST["tgl_lahir"]);
        $pekerjaan = htmlspecialchars($_POST["pekerjaan"]);

        $dateOfBirth = DateTime::createFromFormat('Y-m-d', $tgl_lahir);
        if (!$dateOfBirth) {
            die('Invalid date of birth format. Please use YYYY-MM-DD.');
        }

        $today = new DateTime();
        $umur = $today->diff($dateOfBirth)->y;

        switch ($pekerjaan) {
            case "3D modeling":
                $fee = 5000000;
                break;
            case "freelancer":
                $fee = 4500000;
                break;
            case "kuli":
                $fee = 3500000;
                break;
            default:
                $fee = 0;
        }

        // Display output
        echo "<h2>Output</h2>";
        echo "Nama: $nama<br>";
        echo "Umur: $umur tahun<br>";
        echo "Pekerjaan: $pekerjaan<br>";
        echo "fee: Rp " . number_format($fee, 0, ',', '.') . "<br>";
    }
    ?>
    <br>
    <br>
    <hr class="border-bottom">

    <p class="text-left font-weight-bold ">Tugas pemograman web Raja heppyanto pertemuan 9</p>

</body>
</html>

```
![img](https://github.com/luffy-arc/lab7Web/blob/main/Screenshot%20(47).png)

## OUTPUT

![img](https://github.com/luffy-arc/lab7Web/blob/main/Screenshot%20(46).png)
![img](https://github.com/luffy-arc/lab7Web/blob/main/Screenshot%20(48).png)

## 2. Proses praktikum

* cara menjalankan PHP
  ![img](https://github.com/luffy-arc/lab7Web/blob/main/Screenshot%20(43).png)
  ![img](https://github.com/luffy-arc/lab7Web/blob/main/Screenshot%20(44).png)
  ![img](https://github.com/luffy-arc/lab7Web/blob/main/Screenshot%20(45).png)

