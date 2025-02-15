# Algoritma Warna Pedulilindungi
v. 2.1\
14 September 2021\
\
Berikut ini algoritma yg akan kita implementasi sebagai pembetulan algoritma Pedulilindungi. Hasil diskusi tambahan dengan Litbang dan P2P.


1. 🟢 Hijau: 
- Fully Vaccinated (2x vaksin, dan tidak ada data bahwa dia positif atau kontak erat) 
- 2x24 PCR result negatif OR 1x24 Antigen result negatif
2. 🟡 Kuning:
- Baru vaksin 1x dan tidak ada data bahwa dia positif atau kontak erat
- Penyintas < 3 bulan tidak ada data bahwa dia positif atau kontak erat
3. 🔴 Merah
- Belum vaksin tidak ada data bahwa dia positif atau kontak erat
4. ⚫️ Hitam
- Positif covid 
- Kontak erat

---

Beberapa catatan:
- seluruh data individual checkin dan checkout di pergunakan untuk kebutuhan tracing selama 3 minggu ke depan. Setalah 3 minggu, semua data individual checkin dan checkout di delete permanen dari server</li>
- Untuk komorbid permanen yg tidak bisa di vaksin membutuhkan surat keterangan dokter specialist dan test PCR / antigen diputuskan berdasarkan kebijakan perusahaan untuk karyawan</li>
- Pengunjung mall, retail resto / public area , tamu pabrik hanya boleh hijau dan kuning</li>
- Karyawan yg masuk ketempat kerja warna hijau kuning dan merah diperbolehkan masuk. </li>
- Warna merah masuk ke tempat kerja masih boleh dengan batas waktu 30 sept</li>
<ol type="a">
<li>Jika dalam satu hari ada hasil positif dan negatif dari dua lab yang berbeda maka yang NAR kirim ke PL adalah yang positif</li>

<li>Jika update lab dilakukan setelah batas jam rilis maka dianggap di update 1 hari setelahnya </li>
<li>10 hari sejak positive pertama masih dianggap positive. Walaupun ada hasil negative.</li>
<li>Hasil negatif sebelum 10 hari dari tanggal pengambilan sampel positif tidak akan dikirimkan dari NAR ke PL</li>
<li>hari ke 11 s.d 14 dari positif pertama jika ada inputan test baru dgn hasil negative maka diambil negative dan data ini akan dikirimkan dari NAR ke PL</li>
<li>Bila hari 11 s.d 14 hasil test masih positif maka masih dianggap positive</li>
<li>Bila hari ke 11 s.d 14 tidak tes maka masih dianggap positif</li>
<li>14 hari setelah positif pertama, jika tidak ditemukan data di SIRS Online, maka akan dianggap otomatis negative di hari ke-15 dan di PL akan kembali ke kondisi awal</li>
<li>Jika data ditemukan di SIRS Online dan masih dirawat karena covid/suspect maka status selalu positif</li>
<li>Sampai dengan 30 hari setelah positif pertama, maka hasil positif tidak akan pernah dianggap sebagai re-infeksi</li>
<li>Sampai 90 hari setelah negatif, maka akan dianggap sebagai status 1x suntik – setelah 90 hari akan kembali ke posisi awal (misalnya belum vaksin)</li>
<li>Untuk semua data positif yg ada di PJTLI yg sudah diapprove, maka statusnya adalah positif (hitam)</li>
<li>Data yang terkonfirmasi covid, tapi tidak ada hasil test lab (dimasukkan oleh Dinkes dan PHEOC) termasuk yang akan dianggap positive</li>
<li>Data NIK dari Silacak (program tracing) akan dikategorikan sebagai kontak erat</li>
  <li>Setelah 5 hari (di hari ke 6) kontak erat akan kembali ke posisi awal</li>  
</ol>
