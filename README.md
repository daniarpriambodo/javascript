# javascript
const express = require('express');
const app = express();
const port = 5000;

// Middleware untuk parsing body pada permintaan POST
app.use(express.json());

// Endpoint untuk mendapatkan waktu sekarang
app.get('/waktu', (req, res) => {
  const currentDateTime = new Date().toLocaleString();
  res.json({ waktu: currentDateTime });
});

// Endpoint untuk menghitung jumlah kata dalam kalimat
app.post('/hitung-kata', (req, res) => {
  const { kalimat } = req.body;
  const jumlahKata = kalimat.split(' ').length;
  res.json({ jumlah_kata: jumlahKata });
});

// Endpoint untuk membalikkan string
app.put('/balik-string', (req, res) => {
  const { kata } = req.body;
  const reversedString = kata.split('').reverse().join('');
  res.json({ string_terbalik: reversedString });
});

// Endpoint yang menghasilkan respons acak
app.get('/pesan-acak', (req, res) => {
  const pesanAcak = [
    'Halo!',
    'Selamat datang!',
    'Terima kasih!',
    'Have a nice day!',
    'Semoga harimu menyenangkan!',
  ];
  const randomIndex = Math.floor(Math.random() * pesanAcak.length);
  const pesan = pesanAcak[randomIndex];
  res.json({ pesan: pesan });
});

// Middleware untuk menangani endpoint tidak ditemukan
app.use((req, res) => {
  res.status(404).json({ error: 'Endpoint tidak ditemukan' });
});

// Menjalankan server
app.listen(port, () => {
  console.log(`Server berjalan di http://localhost:${port}`);
});

//Nama : Daniar Priambodo
//NRP : 3323600009
//Kelas : 1 Sains Data Terapan A
