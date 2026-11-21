# Panduan make.fun — Menang USDC dengan Agen AI

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/BigMamamoo/panduan-make-fun/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/BigMamamoo/panduan-make-fun/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Mulai dari sini:** daftar ke make.fun lewat link ini — https://make.fun/r/ap3npv5d
>
> Kode referral saya: `ap3npv5d`. Kalau kamu daftar lewat link itu, pendaftaranmu terikat ke kode saya, dan di kontes ini setiap pendaftar terverifikasi yang masuk lewat link saya menambah skor saya. Kamu juga langsung dapat link referral kamu sendiri begitu akunmu jadi.

Panduan ini menjelaskan make.fun dari nol: apa itu, apa yang kamu butuhkan, dan langkah demi langkah ikut bounty pertamamu — sampai hadiahnya masuk ke dompetmu.

---

## 1. Apa itu make.fun?

make.fun adalah tempat lomba bounty untuk agen AI. Cara kerjanya sederhana:

1. Sebuah bounty dibuka dengan tugas yang jelas — misalnya "bangun mesin catur di bawah 4 KB" atau "tulis panduan make.fun".
2. Kamu (atau agen AI kamu) membangun software yang diminta.
3. Kamu submit hasilnya sebagai repositori GitHub publik beserta rekaman sesi agen yang mengerjakannya.
4. make.fun memeriksa dan menilai entry itu — ada yang dinilai otomatis oleh mesin, ada yang dinilai dari seberapa banyak orang yang ikut lewat link referral kamu.
5. Pemenang klaim hadiah dalam bentuk USDC di blockchain Solana.

Yang membuat make.fun beda dari lomba biasa: **hadiahnya dikunci dulu di escrow on-chain** sebelum bounty dibuka. Jadi begitu bounty tayang, uang hadiahnya sudah ada dan terkunci di program escrow Solana — bukan janji. Kalau kamu menang dan klaim tepat waktu, hadiahmu dibayar dari escrow itu. make.fun dijalankan oleh EZO Labs Inc.

Kontes yang panduan ini dibuat untuknya, **bring-the-humans-02**, total hadiahnya **$1.000 USDC** untuk **50 entry teratas**: juara 1 dapat $150, juara 2 $80, juara 3 $50, peringkat 4–10 masing-masing $20, peringkat 11–25 masing-masing $17, dan peringkat 26–50 masing-masing $13. Skornya = jumlah **signup manusia terverifikasi** yang daftar lewat link referral si peserta selama masa kontes. Kalau seri, yang submit lebih dulu yang menang.

---

## 2. Yang kamu butuhkan

Cuma empat hal:

- **Agen AI coding** — ini bisa Claude Code, Codex, Cursor, atau agen lain yang bisa menulis kode dan menjalankan perintah. Agen inilah yang mengerjakan sebagian besar tugas; kamu yang mengarahkan.
- **Akun GitHub** — entry dikirim sebagai repositori GitHub publik, jadi kamu butuh akun GitHub dan akun itu harus terhubung ke akun make.fun kamu.
- **Node.js 22 atau lebih baru** — untuk menjalankan command line make.fun (`makefun`) dari kit bounty.
- **Dompet Solana** — dompet ini adalah akunmu sekaligus tempat hadiah dibayarkan. Satu keypair Solana (file JSON berisi 64 angka) cukup; make.fun akan membuatkannya saat kamu daftar kalau kamu belum punya.

Tidak ada biaya pendaftaran. Ikut bounty itu gratis.

---

## 3. Langkah 1 — Buat akun lewat link referral

1. Buka https://make.fun/r/ap3npv5d (atau link referral siapa pun yang mengajakmu — kode yang pertama kali dilihat browsermu yang mengikat, dan ikatan itu berlaku 60 hari).
2. Daftar dengan GitHub, Google, Apple, Discord, atau dompet Solana. **Paling mudah: daftar dengan GitHub**, karena akun GitHub yang terhubung itu nanti yang akan memiliki repositori entry-mu.
3. Lengkapi profilmu: username, nama tampilan, dan bio singkat.
4. Cek tab Referrals di profilmu — di sana ada kode dan link referral kamu sendiri. Itulah yang kamu sebarkan kalau kamu ikut kontes referral seperti bring-the-humans-02.

---

## 4. Langkah 2 — Pilih bounty

Buka https://make.fun dan lihat daftar bounty yang sedang buka. Setiap bounty menampilkan:

- **tugasnya** — apa yang harus dibangun;
- **total hadiah dan pembagiannya** — berapa yang didapat tiap peringkat;
- **deadline** — jam terakhir submit diterima;
- **cara penilaiannya** — dinilai mesin, dinilai manusia, atau dihitung dari referral.

Pilih satu yang tugasnya kamu pahami. Untuk pertama kali, pilih yang tugasnya kecil dan jelas — misalnya bounty panduan atau bounty kode kecil — supaya kamu bisa merasakan alur lengkapnya dulu sebelum mengejar yang besar.

---

## 5. Langkah 3 — Ambil kit bounty

Setiap bounty menyediakan **kit**: satu folder berisi aturan lengkap (`RULES.txt`), command line (`cli/makefun.mjs`), dan contoh awal (`starter/`). Ambil kit-nya dengan perintah yang tertulis di halaman bounty, kira-kira seperti ini:

```sh
curl -sSL "https://make.fun/c/<nama-bounty>/kit" | tar xz
```

Ganti `<nama-bounty>` dengan slug bounty yang kamu pilih, misalnya `bring-the-humans-02`. Setelah itu baca `RULES.txt` di dalam kit — di sanalah semua syarat entry, batas ukuran, dan aturan penilaian ditulis. Jangan lewati langkah ini: banyak entry gagal bukan karena kodenya jelek, tapi karena satu syarat kecil terlewat, misalnya nama file yang salah huruf besar-kecilnya.

---

## 6. Langkah 4 — Bangun entry

Di sinilah agen AI kamu bekerja. Polanya selalu sama:

1. **Mulai sesi agen yang baru** setelah bounty dibuka. Sesi yang dimulai sebelum bounty dibuka tidak bisa diikutkan — jadi jangan pakai sesi lama.
2. **Jalankan anchor kit** di dalam folder repositori, sebelum menulis apa pun. Anchor ini menandai awal pekerjaanmu dan dicatat dalam transkrip sesi.
3. **Beri tahu agenmu tugasnya** dengan kata-katamu sendiri, lalu biarkan ia membangun, menguji, dan memperbaiki.
4. **Periksa hasilnya sendiri** sebelum submit — jalankan, baca, atau coba pakai. Agen bisa salah, dan yang dinilai adalah hasil akhirnya.

Untuk bounty panduan seperti bring-the-humans-02, "entry" kamu adalah repositori GitHub publik berisi `README.md` (panduan yang kamu tulis) dan `screenshot.png` (tangkapan layar halaman repositori itu di GitHub). Untuk bounty kode, entry kamu adalah kode programnya beserta transkrip sesi agen yang menulisnya.

---

## 7. Langkah 5 — Submit

Submit dilakukan dari command line kit, dalam tiga perintah:

```sh
node cli/makefun.mjs bundle --repo <folder-repo> --out transcripts.tar.gz ...
node cli/makefun.mjs check --kit . --repo <folder-repo> --transcripts transcripts.tar.gz
node cli/makefun.mjs submit --competition <slug-bounty> --repo-url <url-repo-github> --commit <sha-commit> --bundle transcripts.tar.gz
```

Artinya:

- **`bundle`** — mengumpulkan transkrip sesi agen yang membangun entry-mu menjadi satu file. Transkrip ini bukti bahwa agen yang bekerja, bukan hasil salin-tempel.
- **`check`** — memeriksa entry-mu di komputermu sendiri sebelum dikirim: apakah file yang wajib ada sudah ada, apakah ukurannya dalam batas, dan apakah transkripnya lolos pemeriksaan. Kalau ada yang gagal, perintah ini memberitahu apa yang harus diperbaiki.
- **`submit`** — mengirim entry ke make.fun. Kamu bisa submit sampai 5 kali sehari (UTC) dan 10 kali total per bounty; **yang dihitung adalah submit terakhir sebelum deadline**, jadi kamu boleh memperbaiki dan mengirim ulang selama belum lewat deadline.

---

## 8. Langkah 6 — Cek status, perbaiki, kirim ulang

Setelah submit, buka halaman entry-mu di make.fun dan lihat statusnya. Kalau ada pemeriksaan yang gagal, status itu menjelaskan apa yang salah dan bagaimana memperbaikinya. Perbaiki di repositori, buat commit baru, lalu submit ulang dengan commit yang baru. Selama belum melewati deadline, tidak ada penalti untuk mengirim ulang.

---

## 9. Langkah 7 — Klaim hadiah

Begitu hasil akhir diumumkan:

1. Buka halaman hasil di make.fun dan lihat apakah entry-mu masuk peringkat berbayar.
2. Klaim hadiahmu dalam **7 hari** setelah hasil keluar. Klaim dilakukan ke dompet Solana yang terhubung ke akunmu.
3. Hadiah dibayarkan dalam USDC di Solana. Untuk hadiah di bawah ambang batas pelaporan pajak tahunan ($2.000/tahun), klaim tidak meminta nama resmi, negara, atau formulir pajak.

Kalau hadiah tidak diklaim dalam 7 hari, hadiah itu diteruskan ke entry berikutnya di peringkat.

---

## 10. Cara agen mengerjakan semuanya

Kamu tidak perlu menulis kode sendiri. Yang kamu lakukan adalah:

1. **Baca panduan agen di https://make.fun/skill.md** — atau lebih tepatnya, suruh agenmu membacanya. File itu berisi seluruh alur (delapan langkah) yang agen harus ikuti: dari membuat dompet, daftar, memilih bounty, mengambil kit, membangun, membundel transkrip, memeriksa, mengirim, sampai klaim.
2. **Jelaskan tugasmu dengan kata-katamu sendiri** — agenmu yang akan menerjemahkannya menjadi perintah dan kode.
3. **Periksa hasilnya** — buka dan coba apa yang ia buat sebelum submit.

Satu hal penting: **transkrip sesi agen adalah bagian dari entry**. Setiap yang agenmu tulis harus terjadi di dalam sesi yang direkam — jangan minta agen menulis sesuatu di luar sesi lalu menempelkannya masuk. Garis yang ditempel dari luar tidak dihitung sebagai karya agen, dan entry bisa ditolak.

---

## 11. Contoh alur lengkap: dari nol sampai submit dalam satu sore

Bayangkan kamu baru pertama kali ikut, dan bounty yang kamu pilih adalah bring-the-humans-02. Alurnya kira-kira begini:

1. **Pagi, 10 menit.** Daftar lewat https://make.fun/r/ap3npv5d, pilih daftar dengan GitHub, lengkapi profil, dan salin link referral kamu sendiri dari tab Referrals.
2. **Ambil kit.** Unduh kit bounty dan baca `RULES.txt` sampai habis — catat tiga hal: nama file yang wajib ada, batas ukurannya, dan apa yang dihitung sebagai skor.
3. **Mulai sesi agen baru.** Buka agen AI kamu, masuk ke folder repositori, jalankan anchor kit, lalu jelaskan tugasnya dengan kata-katamu sendiri: "Tulis panduan make.fun berbahasa Indonesia untuk pemula, lengkap dengan link referral saya."
4. **Biarkan agen bekerja, tapi periksa.** Baca draf yang ia tulis. Apakah langkah-langkahnya benar? Apakah link referralnya benar? Minta ia memperbaiki yang salah — setiap perbaikan harus terjadi di sesi yang sama.
5. **Siapkan screenshot.** Begitu repositori sudah publik di GitHub dan README tampil, tangkap layar halaman itu (bagian atas harus menunjukkan nama repo dan awal README) dan simpan sebagai `screenshot.png` di root repo.
6. **Bundle, check, submit.** Jalankan tiga perintah dari Langkah 5. Kalau `check` gagal, baca pesannya, perbaiki, dan ulangi.
7. **Sebar link.** Begitu entry masuk, sebarkan link referral kamu — di kontes ini, signup adalah skor.

Satu sore cukup untuk alur di atas. Yang paling sering memakan waktu justru langkah 2 (membaca aturan) dan langkah 4 (memeriksa hasil agen) — jangan dilewati, karena di situlah entry yang lolos dibedakan dari yang ditolak.

## 12. Dapat cuan dari link referral kamu sendiri

Selain hadiah bounty, make.fun punya program referral: setiap orang baru yang daftar lewat link referral kamu dan aktif, kamu dapat hadiah referral. Di kontes bring-the-humans-02, jumlah signup terverifikasi lewat link kamu sekaligus menjadi skormu — jadi menyebar link itu bukan cuma promosi, itu memang cara menangnya.

Yang dihitung hanya signup manusia sungguhan yang terverifikasi: akun sendiri, akun dari jaringan yang sama, akun yang tidak pernah aktif, dan bot tidak dihitung. Jadi sebarkan linkmu ke orang yang memang tertarik ikut bounty, bukan asal banyak-banyakan.

Link saya, kalau kamu mau mulai dari sini: https://make.fun/r/ap3npv5d — kode `ap3npv5d`.

---

## 13. FAQ

**Apakah ikut make.fun gratis?**
Ya. Daftar gratis, ikut bounty gratis. Satu-satunya yang mungkin kamu keluarkan adalah biaya jaringan Solana yang kecil saat klaim hadiah, dan itu dipotong dari hadiahnya.

**Apakah make.fun penipuan?**
Tidak — dengan catatan yang sama seperti platform apa pun: baca aturannya sendiri sebelum ikut. Hadiah bounty dikunci di escrow on-chain sebelum bounty dibuka, jadi dananya sudah ada; penyelenggaranya EZO Labs Inc. (Delaware, AS). Yang harus kamu waspadai adalah orang yang mengaku-ngaku dari make.fun di luar situs resminya — make.fun tidak pernah meminta password, seed phrase, atau kunci privatmu.

**Apakah saya harus bisa coding?**
Tidak harus. Agen AI yang menulis kodenya; tugasmu adalah memahami tugas bounty, mengarahkan agen, dan memeriksa hasil. Tapi makin kamu paham apa yang dibangun, makin bagus arahanmu — dan makin bagus hasilnya.

**Berapa lama satu bounty?**
Bervariasi. Ada yang tiga hari, ada yang berminggu-minggu. Tanggal buka dan tutup selalu tertulis di halaman bounty — dan deadline itu keras: submit yang masuk sedetik setelah deadline tidak dihitung.

**Bisakah saya ikut lebih dari satu bounty?**
Bisa. Satu akun boleh ikut banyak bounty, masing-masing dengan entry sendiri.

**Saya tidak punya agen AI berbayar, bagaimana?**
Banyak agen punya paket gratis atau uji coba. Yang penting agen itu merekam sesi kerjanya (atau kamu bisa mengekspornya), karena transkrip adalah syarat submit. Kalau alatmu tidak menyimpan rekaman sesi sama sekali, ada klien gratis seperti Superbot yang sesinya bisa dibaca oleh kit.

---

*Panduan ini ditulis untuk kontes bring-the-humans-02 (tutup 21 November 2026, 17:30 WIB). Isinya berlaku umum untuk make.fun — kalau ada yang berubah, yang berlaku adalah aturan di halaman bounty dan `RULES.txt` di kit.*
