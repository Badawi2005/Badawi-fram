<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>BADAWI FRAM - Jual Telur</title>
  <style>
    /* Background gambar full */
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-image: url('images/background.jpg'); /* ganti dengan gambar ayam/telur */
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
    }

    /* Header */
    header {
      background: rgba(255, 204, 0, 0.85); /* semi-transparan */
      padding: 20px;
      text-align: center;
      backdrop-filter: blur(4px);
    }
    header h1 {
      margin: 0;
      color: #333;
    }
    .logo {
      width: 150px;
      margin-bottom: 10px;
    }

    /* Container */
    .container {
      padding: 20px;
      max-width: 600px;
      margin: 40px auto;
      background: rgba(255, 255, 255, 0.95); /* putih semi-transparan */
      border-radius: 12px;
      box-shadow: 0 4px 16px rgba(0,0,0,0.2);
    }

    .price {
      font-size: 20px;
      color: #2e7d32;
      margin: 10px 0;
      font-weight: bold;
    }

    label, select, input {
      display: block;
      width: 100%;
      margin-top: 10px;
      font-weight: bold;
    }
    select, input {
      padding: 10px;
      border-radius: 6px;
      border: 1px solid #ccc;
      font-size: 16px;
    }

    button {
      margin-top: 20px;
      padding: 14px;
      width: 100%;
      border: none;
      border-radius: 6px;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    .btn-green { background: #25D366; color: #fff; }
    .btn-yellow { background: #ffcc00; color: #333; }
    .btn-green:hover { background: #1ebe5a; transform: scale(1.03); }
    .btn-yellow:hover { background: #e6b800; transform: scale(1.03); }

    footer {
      text-align: center;
      margin-top: 30px;
      color: #fff;
      font-size: 14px;
      text-shadow: 1px 1px 2px #000;
    }

    img.main-photo {
      width: 100%;
      border-radius: 10px;
      margin-top: 15px;
    }

  </style>
</head>
<body>

  <header>
    <img src="images/logo.png" alt="BADAWI FRAM Logo" class="logo" />
    <h1>BADAWI FRAM</h1>
    <p>Jual Telur Ayam Segar</p>
    <p>Alamat: JALAN RANGGA KUSUMA SLAGI RT 13 RW 3</p>
  </header>

  <div class="container">
    <img src="images/main.png" class="main-photo" alt="Telur BADAWI FRAM">

    <label for="jenis">Pilih Jenis Harga</label>
    <select id="jenis" onchange="setHarga()">
      <option value="25800">Grosir - Rp 25.800 / kg</option>
      <option value="27000">Ecer - Rp 27.000 / kg</option>
    </select>

    <label for="inputHarga">Harga per Kg (Rp)</label>
    <input type="number" id="inputHarga" value="25800" readonly />

    <label for="inputKg">Jumlah (Kg)</label>
    <input type="number" id="inputKg" placeholder="Contoh: 2" />

    <div class="price" id="total">Total: Rp 0</div>

    <button class="btn-yellow" onclick="hitungTotal()">Hitung Total</button>
    <button class="btn-green" onclick="orderWhatsApp()">Order via WhatsApp</button>
  </div>

  <footer>
    © 2026 BADAWI FRAM
  </footer>

  <script>
    function setHarga() {
      const harga = document.getElementById('jenis').value;
      document.getElementById('inputHarga').value = harga;
    }

    function hitungTotal() {
      const harga = document.getElementById('inputHarga').value;
      const kg = document.getElementById('inputKg').value;
      if(harga > 0 && kg > 0) {
        const total = harga * kg;
        document.getElementById('total').innerText = 'Total: Rp ' + total;
      } else {
        alert('Masukkan harga dan jumlah kg');
      }
    }

    function orderWhatsApp() {
      const harga = document.getElementById('inputHarga').value;
      const kg = document.getElementById('inputKg').value;
      const total = harga * kg;
      const jenis = document.getElementById('jenis').options[document.getElementById('jenis').selectedIndex].text;
      const pesan = `Halo BADAWI FRAM, saya mau pesan telur. ${jenis}, Jumlah: ${kg} kg, Total: Rp ${total}`;
      const noWA = '6282132698172';
      const url = `https://wa.me/${noWA}?text=${encodeURIComponent(pesan)}`;
      window.open(url, '_blank');
    }
  </script>
</body>
</html>
