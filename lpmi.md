# ANALISIS KOMPREHENSIF LEMBAGA PENJAMINAN MUTU INTERNAL (LPMI)
## Struktur Organisasi, Integrasi Lintas Unit, dan Implementasi Siklus PPEPP
### Dokumen Referensi untuk Pengembangan Modul e-SPMI pada Sistem Informasi Akademik

---

## 0. RINGKASAN EKSEKUTIF & CATATAN REGULASI TERKINI (Agustus 2026)

Dokumen ini disusun sebagai kajian menyeluruh atas kerja Lembaga Penjaminan Mutu Internal (LPMI) di perguruan tinggi Indonesia, mencakup dasar hukum, kedudukan kelembagaan, struktur organisasi, jejaring integrasi ke seluruh unit (fakultas, program studi, unit pendukung), dokumen wajib, kerangka standar mutu, mekanisme siklus PPEPP, Audit Mutu Internal (AMI), Rapat Tinjauan Manajemen (RTM), keterkaitan dengan akreditasi eksternal (SPME), periodisasi kegiatan mutu, hingga rekomendasi arsitektur fitur sistem informasi.

**Landasan regulasi yang berlaku saat dokumen ini disusun:**

| Regulasi | Status | Keterangan |
|---|---|---|
| UU No. 12 Tahun 2012 tentang Pendidikan Tinggi | Berlaku | Landasan konstitusional SPM Dikti |
| Permenristekdikti No. 62 Tahun 2016 | **Dicabut** | Diganti Permendikbudristek 53/2023 |
| Permendikbud No. 3 & No. 5 Tahun 2020 (SN Dikti & Akreditasi) | **Dicabut** | Diganti Permendikbudristek 53/2023 |
| Permendikbudristek No. 53 Tahun 2023 | **Dicabut** sejak 2 September 2025 | Diganti Permendiktisaintek 39/2025 |
| **Permendiktisaintek No. 39 Tahun 2025** | **BERLAKU (aturan pokok saat ini)** | Ditetapkan 28 Agustus 2025, mulai berlaku 2 September 2025 |
| **Permendiktisaintek No. 10 Tahun 2026** | **BERLAKU (aturan perubahan/penegasan)** | Diundangkan 16 Juli 2026; mengubah 26 ketentuan Pasal 14–113 Permen 39/2025, fokus penyempurnaan mekanisme akreditasi & tata kelola BAN-PT/LAM |
| Kepmendiktisaintek No. 358/M/KEP/2025 | Berlaku mulai 2026 | Perluasan Indikator Kinerja Utama (IKU) dari 8 menjadi 12 poin |

**Poin penting untuk Universitas Rokania:** Masa transisi penyesuaian SPMI internal terhadap Permendiktisaintek 39/2025 diberikan selama **2 tahun sejak diundangkan** (artinya jatuh tempo sekitar September 2027). Karena LED LAMDIK PTI sedang disusun sekarang, struktur standar dan istilah yang dipakai dalam LED sebaiknya sudah diselaraskan dengan nomenklatur baru (Standar Luaran–Proses–Masukan, status "Terakreditasi/Terakreditasi Unggul/Tidak Terakreditasi") agar tidak perlu revisi besar saat LAMDIK mengadopsi instrumen barunya.

---

## 1. LANDASAN HUKUM & EVOLUSI REGULASI SPMI

Evolusi regulasi SPMI di Indonesia penting dipahami karena banyak template dokumen SPMI yang beredar di internet (dan mungkin dipakai LPMI Rokania) masih mengacu pada regulasi lama:

```
UU No. 12/2012 (Dikti)
   │
   ├─ Permenristekdikti 62/2016 (SPM Dikti) ─────────┐
   ├─ Permendikbud 3/2020 (SN Dikti, 24 standar)      │  DICABUT
   ├─ Permendikbud 5/2020 (Akreditasi)                │
   │                                                    ▼
   └─────────► Permendikbudristek 53/2023 ─── DICABUT 2 Sept 2025
                        │
                        ▼
              Permendiktisaintek 39/2025 (berlaku 2 Sept 2025)
                        │
                        ▼
              Permendiktisaintek 10/2026 (16 Jul 2026, PENEGASAN/PERUBAHAN
              — bukan pencabutan, 26 poin Pasal 14–113)
```

**Empat pilar SPM Dikti yang konsisten dipertahankan di semua generasi regulasi:**
1. Standar Nasional Pendidikan Tinggi (SN Dikti)
2. Sistem Penjaminan Mutu Internal (SPMI)
3. Sistem Penjaminan Mutu Eksternal (SPME) / Akreditasi
4. Pangkalan Data Pendidikan Tinggi (PD Dikti)

Perubahan paling substansial pada Permendiktisaintek 39/2025 bukan pada mekanisme PPEPP-nya (yang dipertahankan), melainkan pada **filosofi mutu**: standar institusi wajib memuat pelampauan (bukan sekadar pemenuhan) terhadap SN Dikti — baik dari sisi tingkat mutu maupun keluasan substansi — dan pada **penyederhanaan status akreditasi**.

---

## 2. ARSITEKTUR BESAR SISTEM PENJAMINAN MUTU PENDIDIKAN TINGGI (SPM DIKTI)

```
                         ┌─────────────────────────┐
                         │   PENDIDIKAN TINGGI      │
                         │       BERMUTU            │
                         └────────────▲─────────────┘
                                      │
        ┌─────────────────────────────┼─────────────────────────────┐
        │                             │                             │
┌───────▼────────┐          ┌─────────▼─────────┐          ┌────────▼────────┐
│   SN DIKTI      │          │       SPMI          │          │      SPME        │
│ (standar minimal│◄────────►│  (Siklus PPEPP,      │◄────────►│  (Akreditasi:     │
│  yg WAJIB        │ acuan   │  dijalankan otonom   │ hasil    │  BAN-PT utk PT,   │
│  dilampaui)       │         │  oleh PT sendiri)    │  audit   │  LAM utk Prodi)   │
└─────────────────┘          └──────────────────────┘          └──────────────────┘
        │                             │                             │
        └─────────────────────────────┴─────────────────────────────┘
                                      │
                         ┌────────────▼─────────────┐
                         │   PANGKALAN DATA DIKTI    │
                         │      (PD DIKTI)           │
                         │  sumber evidensi & basis  │
                         │  prinsip TRIANGULASI      │
                         └───────────────────────────┘
```

**Prinsip triangulasi** (ditegaskan Pasal 66 Permendiktisaintek 39/2025): kebenaran mutu digali melalui berbagai sumber data dan sudut pandang yang saling melengkapi — dokumen SPMI, data PD Dikti, dan hasil asesmen eksternal harus **konsisten satu sama lain**. Ini sangat relevan untuk kasus Anda: temuan kontradiksi data internal di LED LAMDIK adalah persis jenis masalah yang prinsip triangulasi ini coba cegah — kalau LPMI berfungsi baik, data di LED, di PD Dikti, dan di laporan AMI semestinya saling mengonfirmasi, bukan saling bertentangan.

---

## 3. KEDUDUKAN & FUNGSI LPMI DALAM TATA KELOLA PERGURUAN TINGGI

### 3.1 Dasar Pembentukan
LPMI (nomenklatur bisa berbeda antar-PT: LPM, LPMI, BPM, BAMI, SPI-Mutu — sesuai Statuta masing-masing) dibentuk melalui:
- **Statuta Perguruan Tinggi** (mengatur kedudukan sebagai unsur pelaksana non-akademik/lembaga setingkat LPPM)
- **SK Rektor** (mengangkat Kepala/Ketua LPMI dan struktur di bawahnya)
- Untuk PTS di bawah yayasan (seperti Universitas Rokania di bawah Yayasan Rokan Riau Raya): biasanya memerlukan **persetujuan/pertimbangan Badan Penyelenggara** untuk kebijakan mutu strategis, sesuai penegasan Permendiktisaintek 39/2025 bahwa rancangan SPMI ditetapkan pemimpin PT "setelah mendapat pertimbangan Senat PT (dan badan penyelenggara PT jika PTS)".

### 3.2 Kedudukan dalam Struktur Organisasi
LPMI berada **langsung di bawah Rektor**, sejajar secara struktural dengan lembaga lain seperti LPPM, namun memiliki sifat **lintas-fungsi (cross-cutting)** — artinya garis koordinasinya menembus ke semua fakultas, prodi, dan unit, tidak seperti LPPM yang lingkupnya spesifik penelitian/PkM.

```
                    ┌───────────────┐
                    │  YAYASAN /    │
                    │  BADAN         │◄── pertimbangan kebijakan mutu (PTS)
                    │  PENYELENGGARA │
                    └───────┬───────┘
                            │
                    ┌───────▼───────┐        ┌──────────────┐
                    │    REKTOR      │◄──────►│    SENAT      │
                    │  (& Wakil       │ pertim │  UNIVERSITAS  │
                    │   Rektor)       │ bangan │ (pengesahan   │
                    └───────┬───────┘  standar│  kebijakan &   │
                            │                  │  standar mutu) │
          ┌─────────────────┼─────────────────┴──────────────┘
          │                 │                 │
   ┌──────▼──────┐   ┌──────▼──────┐   ┌──────▼──────┐
   │    LPMI      │   │    LPPM      │   │  Biro/Unit   │
   │ (Penjaminan  │◄─►│ (Penelitian  │   │  lain        │
   │  Mutu)       │   │  & PkM)      │   │ (BAAK, SDM,  │
   └──────┬──────┘   └─────────────┘   │  Keuangan,   │
          │  koordinasi PPEPP           │  Sarpras dst)│
          │  ke seluruh unit            └──────────────┘
          │
   ┌──────▼─────────────────────────────────────────────┐
   │                    FAKULTAS                          │
   │  Dekan ──► GPM/UPM Fakultas (Gugus/Unit Penjaminan   │
   │            Mutu tingkat Fakultas)                    │
   └──────┬────────────────────────────────────────────┘
          │
   ┌──────▼─────────────────────────────────────────────┐
   │                 PROGRAM STUDI                        │
   │  Kaprodi ──► GKM/UPPS (Gugus Kendali Mutu /          │
   │              Unit Pengelola Program Studi)            │
   │              — GARIS DEPAN pelaksanaan standar         │
   └───────────────────────────────────────────────────┘
```

### 3.3 Tugas Pokok dan Fungsi (Tupoksi) LPMI
1. **Merumuskan dan mengusulkan** Kebijakan Mutu, Manual Mutu, dan Standar Mutu (tahap Penetapan/P1) untuk disahkan Rektor setelah pertimbangan Senat.
2. **Mengoordinasikan pelaksanaan** standar di seluruh unit (memfasilitasi, bukan mengerjakan langsung — pelaksanaan tetap tanggung jawab unit masing-masing).
3. **Merancang dan menjalankan instrumen evaluasi**: monitoring-evaluasi (monev) pembelajaran, survei kepuasan, dan Audit Mutu Internal (AMI).
4. **Mengelola sistem dokumentasi mutu** (versi dokumen, SK penetapan, bukti pelaksanaan/evidence).
5. **Memfasilitasi Rapat Tinjauan Manajemen (RTM)** di tingkat universitas dan mendorong replikasinya di tingkat fakultas/prodi.
6. **Menjadi simpul data** untuk kebutuhan SPME — menyiapkan/mengoordinasikan penyusunan LED (Laporan Evaluasi Diri) dan LKPS (Laporan Kinerja Program Studi) bekerja sama dengan prodi/fakultas.
7. **Memantau capaian Indikator Kinerja Utama (IKU)** dan indikator kinerja tambahan (IKT) yang ditetapkan PT.
8. **Membina budaya mutu** — pelatihan auditor internal, sosialisasi standar, workshop AMI.
9. **Melaporkan** hasil kerja secara berkala kepada Rektor dan Senat.

### 3.4 Wewenang yang TIDAK Dimiliki LPMI (penting untuk desain sistem)
- LPMI **tidak berwenang mengeksekusi** perbaikan di unit lain — ia hanya merekomendasikan dan memverifikasi tindak lanjut (fungsi kontrol, bukan eksekutif).
- LPMI **tidak menggantikan** fungsi akreditasi eksternal — SPMI dan SPME adalah dua sistem berbeda yang saling menguatkan lewat data, bukan satu proses yang sama.
- Penetapan standar akhir tetap ada di tangan **Rektor** (setelah pertimbangan Senat), LPMI hanya perumus/pengusul teknis.

---

## 4. STRUKTUR ORGANISASI INTERNAL LPMI

Struktur internal LPMI lazimnya terdiri dari:

| Jabatan | Fungsi Utama |
|---|---|
| **Ketua/Kepala LPMI** | Penanggung jawab keseluruhan, pelapor langsung ke Rektor, memimpin RTM tingkat universitas bersama Rektor |
| **Sekretaris LPMI** | Administrasi, penjadwalan, kesekretariatan dokumen |
| **Kepala Bidang Pengembangan Standar & Dokumen (Penetapan)** | Merumuskan/merevisi Kebijakan-Manual-Standar-Formulir mutu; menyusun rumusan ABCD standar |
| **Kepala Bidang Audit Mutu Internal (Evaluasi)** | Mengelola pool auditor, menjadwalkan AMI, memverifikasi Laporan Hasil Audit |
| **Kepala Bidang Monitoring, Data & Pelaporan** | Mengelola sistem informasi mutu, dashboard capaian, data untuk SPME/LED/LKPS, integrasi PD Dikti |
| **Kepala Bidang Pengembangan SDM Mutu/Pelatihan** | Pelatihan auditor, sosialisasi budaya mutu, workshop |
| **Staf Administrasi** | Dukungan operasional harian |

Untuk PT berskala menengah seperti Universitas Rokania, struktur ini bisa dipadatkan (misalnya 1 Kepala + 2 Koordinator Bidang + staf), tetapi **empat fungsi inti (Penetapan, Pelaksanaan-fasilitasi, Evaluasi/Audit, Data-Pelaporan) tetap harus ada perannya** meskipun dirangkap orang yang sama.

---

## 5. PETA INTEGRASI LPMI KE SELURUH UNIT

### 5.1 Ke Fakultas
- **Dekan** bertanggung jawab atas pelaksanaan standar mutu di tingkat fakultas dan pembentukan **GPM/UPM Fakultas**.
- GPM Fakultas berfungsi sebagai **jembatan** antara kebijakan LPMI pusat dan pelaksanaan riil di prodi-prodi di bawahnya; mengoordinasikan monev antar-prodi dalam satu fakultas, mengagregasi data untuk dilaporkan ke LPMI.
- Fakultas juga menjadi tempat pelaksanaan **RTM tingkat fakultas** sebagai turunan dari RTM universitas.

### 5.2 Ke Program Studi (garis depan/frontline)
- **Ketua Program Studi** adalah penanggung jawab utama pelaksanaan (P2) dan objek utama audit (E) karena prodi adalah unit akreditasi (LAM mengakreditasi prodi, bukan fakultas).
- **GKM/UPPS Prodi** bertugas: menjalankan monev pembelajaran per mata kuliah/dosen, mengelola RPS (Rencana Pembelajaran Semester), menghimpun bukti fisik pelaksanaan standar pendidikan, menyiapkan draf LED/LKPS bahan akreditasi LAM.
- Untuk kasus PTI Universitas Rokania yang sedang menyusun LED LAMDIK: **GKM Prodi PTI adalah aktor kunci** yang seharusnya menjadi sumber data pertama sebelum data naik ke GPM Fakultas Filkom lalu ke LPMI pusat — kontradiksi data internal yang Anda temukan biasanya muncul justru karena jalur pelaporan berjenjang ini terputus (prodi mengisi LED langsung tanpa verifikasi berlapis via GPM/LPMI).

### 5.3 Ke Unit Pendukung (objek Standar Non-Akademik)
| Unit | Standar yang Diaudit |
|---|---|
| BAAK/Biro Akademik | Standar proses pembelajaran, administrasi akademik, kalender akademik |
| SDM/Kepegawaian | Standar dosen & tenaga kependidikan (kualifikasi, rasio, beban kerja) |
| Keuangan | Standar pembiayaan pendidikan |
| Sarana-Prasarana/IT | Standar sarana-prasarana, sistem informasi |
| Perpustakaan | Standar sumber belajar |
| LPPM | Standar penelitian & pengabdian masyarakat (koordinasi horizontal, bukan vertikal ke LPMI) |
| Kemahasiswaan & Alumni | Standar kemahasiswaan, tracer study lulusan (relevan untuk IKU) |
| Kerja sama/Humas | Standar kerja sama, hilirisasi (relevan untuk IKU baru 2026) |

### 5.4 Auditor Mutu Internal (Lintas Fungsi)
Auditor **bukan** struktur permanen LPMI, melainkan **dosen/tendik dari unit lain** yang ditunjuk via SK Rektor dan dilatih/disertifikasi LPMI, dengan prinsip **independensi**: auditor tidak boleh mengaudit unit tempatnya sendiri bertugas (menghindari conflict of interest). Pool auditor ini idealnya diambil lintas fakultas (misalnya dosen Filkom mengaudit prodi di fakultas lain, dan sebaliknya).

### 5.5 Mahasiswa
Terlibat sebagai **sumber data**, bukan pelaksana: responden survei kepuasan, kadang dilibatkan sebagai peninjau dalam wawancara AMI khusus standar kemahasiswaan.

---

## 6. LIMA DOKUMEN INTI SPMI

Permendiktisaintek 39/2025 tetap menganut prinsip fleksibilitas bentuk dokumen (tidak harus terpisah judul-per-judul), namun secara substansi lima jenis dokumen berikut tetap diperlukan:

| No | Dokumen | Isi | Ditetapkan Oleh |
|---|---|---|---|
| 1 | **Kebijakan SPMI** | Garis besar filosofi mutu, visi mutu PT, prinsip PPEPP, ruang lingkup | Rektor (SK), pertimbangan Senat |
| 2 | **Manual SPMI / Manual Mutu** | Prosedur teknis tiap tahap PPEPP untuk tiap standar (5 manual per standar: manual penetapan, pelaksanaan, evaluasi, pengendalian, peningkatan) | LPMI, disahkan Rektor |
| 3 | **Standar SPMI/Standar Dikti** | Rumusan pernyataan standar format **ABCD** (Audience–Behaviour–Competence–Degree), memuat indikator capaian; **wajib melampaui SN Dikti** | LPMI usul → Senat pertimbangkan → Rektor tetapkan |
| 4 | **Formulir/Borang SPMI** | Instrumen operasional: form monev, checklist AMI, kuesioner survei, form RTL | LPMI (teknis) |
| 5 | **SOP turunan standar** (opsional tapi lazim) | Prosedur operasional baku per aktivitas (mis. SOP penyusunan RPS, SOP bimbingan skripsi/tugas akhir) | Unit terkait + LPMI |

Rumusan **ABCD** contoh (relevan untuk Standar Luaran Prodi PTI):
> *Audience*: Lulusan Program Studi PTI
> *Behaviour*: mampu merancang dan mengimplementasikan sistem informasi berbasis web
> *Competence*: dengan menerapkan prinsip rekayasa perangkat lunak yang benar
> *Degree*: dibuktikan dengan portofolio proyek yang dinilai kelayakannya oleh dua penguji minimal skor 80

---

## 7. KERANGKA STANDAR MUTU (Isi/Substansi)

Permendiktisaintek 39/2025 menyederhanakan Standar Nasional Pendidikan (dari 8 standar era Permendikbud 3/2020) menjadi **3 komponen utama**:

1. **Standar Luaran** — kriteria minimal kompetensi lulusan (sikap, keterampilan, pengetahuan) yang dirumuskan dalam Capaian Pembelajaran Lulusan (CPL).
2. **Standar Proses** — kriteria minimal proses pembelajaran dan penilaian untuk mencapai standar luaran.
3. **Standar Masukan** — meliputi standar dosen & tenaga kependidikan, isi kurikulum, sarana-prasarana, dan pembiayaan.

Ditambah dua pilar Tridharma lain yang tetap berdiri sendiri:
4. **Standar Penelitian**
5. **Standar Pengabdian kepada Masyarakat (PkM)**

Dan standar tambahan otonom sesuai kebutuhan institusi (non-akademik): tata kelola, kerja sama, sistem informasi, kemahasiswaan, dsb. — jumlah dan namanya **bebas ditentukan PT** (tidak lagi terpatok "24 standar" seperti era sebelumnya).

**Yang berubah secara filosofis dan wajib direfleksikan di setiap rumusan standar baru:** setiap standar institusi (bukan hanya standar dikti minimal) harus memuat pernyataan yang **melampaui SN Dikti**, baik dari sisi angka/target (tingkat mutu) maupun cakupan (keluasan substansi). Contoh praktis: jika SN Dikti mensyaratkan rasio dosen:mahasiswa maksimal 1:30 untuk rumpun tertentu, standar mutu PTI Rokania semestinya menetapkan target internal yang lebih ketat (misal 1:25) sebagai bukti pelampauan, bukan sekadar menyalin angka SN Dikti apa adanya — ini poin yang akan langsung dilihat asesor LAMDIK sebagai indikator kematangan SPMI.

---

## 8. SIKLUS PPEPP — DETAIL LENGKAP PER TAHAP

```
        ┌──────────► P — PENETAPAN ────────────┐
        │         (Standar dirumuskan,          │
        │          disahkan Rektor via SK)       │
        │                                          ▼
   P — PENINGKATAN                          P — PELAKSANAAN
   (RTM, revisi standar,                    (Unit menjalankan
    kaizen/benchmark,                        standar, dokumentasi
    siklus naik ke standar                   bukti pelaksanaan)
    lebih tinggi)                                   │
        ▲                                           ▼
        │                                  E — EVALUASI
        │                              (Monev berkala + AMI:
        └──── P — PENGENDALIAN ◄────── audit, temuan, PTK)
              (Unit tindak lanjuti
               temuan via RTL,
               LPMI verifikasi closing)
```

### 8.1 Penetapan (P1)
| Aspek | Detail |
|---|---|
| **Aktor** | LPMI (perumus) → Senat (pertimbangan) → Rektor (penetapan via SK) |
| **Input** | Visi-misi PT, SN Dikti (sebagai batas minimal wajib dilampaui), hasil evaluasi diri, benchmark PT lain, masukan stakeholder |
| **Proses** | Merumuskan pernyataan standar (format ABCD), menyusun indikator capaian & target, menyusun manual/SOP pelaksanaan |
| **Output** | SK Rektor tentang Kebijakan/Manual/Standar SPMI |
| **Periode tipikal** | Siklus besar (revisi menyeluruh): mengikuti periode Renstra (4–5 tahun). Revisi standar individual: bisa tahunan mengikuti hasil RTM |

### 8.2 Pelaksanaan (P2)
| Aspek | Detail |
|---|---|
| **Aktor** | Semua unit pelaksana: Fakultas (GPM), Prodi (GKM), unit pendukung |
| **Input** | Standar & SOP yang sudah ditetapkan |
| **Proses** | Menjalankan aktivitas Tridharma & administrasi sesuai standar; mendokumentasikan bukti (dokumen, laporan, screenshot sistem, rekaman) |
| **Output** | Bukti pelaksanaan (evidence) — inilah yang nanti jadi lampiran LED/LKPS |
| **Periode tipikal** | Kontinu, berjalan sepanjang semester/tahun akademik |

### 8.3 Evaluasi (E)
Terbagi dua mekanisme:

**a) Monitoring-Evaluasi (Monev) rutin** — dilakukan unit sendiri/GKM-GPM, sifatnya self-assessment berkala:
- Monev pembelajaran (kehadiran dosen, kesesuaian RPS, umpan balik mahasiswa) — biasanya **2x/semester** (tengah & akhir semester)
- Survei kepuasan (mahasiswa, dosen, tendik, pengguna lulusan, mitra) — umumnya **1–2x/tahun**
- Evaluasi capaian pembelajaran lulusan — saat yudisium

**b) Audit Mutu Internal (AMI)** — dilakukan pihak independen (auditor lintas unit), sifatnya **verifikasi eksternal-internal**, lebih formal (lihat Bab 9). Periode tipikal: **1x/tahun**, dijadwalkan menjelang akhir tahun akademik.

### 8.4 Pengendalian (P3)
| Aspek | Detail |
|---|---|
| **Aktor** | Unit yang diaudit (menindaklanjuti) + LPMI (memverifikasi) |
| **Proses** | Unit menyusun **Rencana Tindak Lanjut (RTL)** atas setiap temuan/PTK dari AMI; LPMI memantau progres dan memverifikasi penutupan (*closing*) temuan |
| **Output** | Dokumen RTL, status closing temuan (open/in-progress/closed) |
| **Periode tipikal** | 1–3 bulan setelah AMI selesai, sebelum RTM |

### 8.5 Peningkatan (P4)
| Aspek | Detail |
|---|---|
| **Aktor** | Pimpinan PT (Rektor, WR), Dekan, Kaprodi, LPMI — forum **Rapat Tinjauan Manajemen (RTM)** |
| **Proses** | Mengevaluasi keseluruhan siklus: hasil AMI, capaian standar/IKU, umpan balik stakeholder, efektivitas RTL → memutuskan langkah peningkatan (revisi standar ke level lebih tinggi, benchmarking, realokasi sumber daya) |
| **Output** | Notulen RTM, keputusan strategis, usulan revisi standar → **kembali ke tahap Penetapan** (siklus spiral, bukan lingkaran statis — semangat *continuous quality improvement*) |
| **Periode tipikal** | 1x/tahun, biasanya setelah AMI dan sebelum penyusunan RKAT tahun berikutnya |

---

## 9. AUDIT MUTU INTERNAL (AMI) — MEKANISME RINCI

### 9.1 Tahapan Pelaksanaan
1. **Perencanaan** — LPMI menyusun jadwal audit tahunan, menentukan ruang lingkup (unit/prodi mana saja), menugaskan auditor (dengan aturan independensi: auditor ≠ unit yang diaudit).
2. **Pelatihan/penyegaran auditor** — sebelum audit, jika ada auditor baru atau ada perubahan instrumen.
3. **Pemeriksaan kecukupan (desk evaluation)** — auditor memeriksa dokumen yang diunggah auditee (evidence pelaksanaan standar) sebelum turun lapangan.
4. **Rapat pembukaan (opening meeting)** — auditor menjelaskan ruang lingkup & jadwal kepada auditee.
5. **Asesmen lapangan (visitasi)** — wawancara, observasi, verifikasi silang dokumen vs. praktik nyata.
6. **Rapat penutupan (closing meeting)** — auditor menyampaikan temuan sementara kepada auditee (transparansi, sesuai prinsip tata kelola PPEPP).
7. **Penyusunan Laporan Hasil Audit (LHA)** — dituangkan formal, termasuk kategori temuan.

### 9.2 Kategori Temuan
| Kategori | Arti | Konsekuensi |
|---|---|---|
| **KTS Mayor** (Ketidaksesuaian Mayor) | Standar tidak dilaksanakan sama sekali / berulang | Wajib RTL segera, verifikasi ketat |
| **KTS Minor** | Pelaksanaan ada tapi tidak konsisten/tidak lengkap bukti | Wajib RTL, batas waktu lebih longgar |
| **Observasi (OB)** | Potensi risiko ke depan, belum jadi masalah nyata | Dicatat sebagai perhatian, tidak wajib RTL formal |
| **OFI** (*Opportunity for Improvement*) | Saran peningkatan meski standar sudah terpenuhi | Masukan untuk siklus Peningkatan |

### 9.3 Tindak Lanjut
Setiap KTS memicu **Permintaan Tindakan Koreksi (PTK)** kepada unit auditee → unit menyusun **RTL** dengan penanggung jawab dan tenggat waktu → LPMI memverifikasi bukti perbaikan → status ditutup (*closed*) atau dieskalasi jika tidak selesai tepat waktu.

**Catatan praktis relevan untuk LED LAMDIK Anda saat ini:** kontradiksi data internal yang ditemukan di LED sebenarnya adalah "temuan AMI" versi manual yang harusnya sudah tertangkap lebih dini kalau siklus AMI internal berjalan rutin sebelum penyusunan LED — ini justru argumen kuat untuk memperkuat modul AMI di SIAKAD supaya kejadian serupa tidak berulang di siklus akreditasi berikutnya.

---

## 10. RAPAT TINJAUAN MANAJEMEN (RTM)

**Peserta:** Rektor & Wakil Rektor, Dekan, Ketua Prodi, Kepala LPMI beserta tim, kepala unit pendukung terkait.

**Agenda standar (mengikuti pola manajemen mutu umum):**
1. Tindak lanjut keputusan RTM sebelumnya
2. Hasil AMI periode berjalan (ringkasan temuan & status RTL)
3. Umpan balik stakeholder (hasil survei kepuasan mahasiswa/dosen/tendik/pengguna lulusan/mitra)
4. Capaian standar mutu & Indikator Kinerja Utama (IKU)
5. Status tindakan korektif & preventif
6. Perubahan yang berdampak pada SPMI (regulasi baru, kebijakan pimpinan, kondisi eksternal)
7. Rekomendasi peningkatan mutu untuk siklus berikutnya

**Output:** Notulen RTM formal, daftar keputusan strategis dengan penanggung jawab & tenggat, dasar untuk revisi standar (kembali ke tahap Penetapan).

**Periode tipikal:** minimal 1x/tahun di tingkat universitas (banyak PT menjalankannya 2x/tahun — awal & akhir tahun akademik), dan idealnya direplikasi dalam skala lebih kecil di tingkat fakultas/prodi menjelang RTM universitas agar data yang naik sudah matang.

---

## 11. INTEGRASI SPMI ↔ SPME (AKREDITASI) & PD DIKTI

### 11.1 Perubahan Status Akreditasi (Permendiktisaintek 39/2025)
Status akreditasi disederhanakan dari sistem berjenjang lama (A/B/C atau Unggul/Baik Sekali/Baik) menjadi **tiga status saja**:
- **Terakreditasi** — PT/Prodi memenuhi SN Dikti
- **Terakreditasi Unggul** — PT/Prodi melampaui SN Dikti
- **Tidak Terakreditasi** — PT/Prodi tidak memenuhi SN Dikti

### 11.2 Kewenangan Lembaga Akreditasi
- **BAN-PT** → akreditasi tingkat **perguruan tinggi (institusi)**
- **LAM** (sesuai rumpun ilmu, untuk kasus Anda: **LAMDIK** untuk rumpun kependidikan) → akreditasi tingkat **program studi**

### 11.3 Ketentuan Waktu Pengajuan (Pasal 77)
PT/Prodi yang baru memperoleh status **"Terakreditasi Pertama"** (otomatis saat izin penyelenggaraan terbit) **wajib mengajukan permohonan akreditasi** ke BAN-PT/LAM dalam **waktu maksimal 2 tahun** sejak mulai beroperasi untuk memperoleh status definitif (Terakreditasi/Terakreditasi Unggul).

### 11.4 Efisiensi berbasis PD Dikti
Perpanjangan status "Terakreditasi" ke depan diarahkan memanfaatkan data dari PD Dikti untuk meminimalkan beban administratif submission ulang — implikasinya: **kualitas dan konsistensi data yang di-input rutin ke PD Dikti kini punya bobot langsung terhadap proses akreditasi**, bukan sekadar syarat administratif tahunan. Ini argumen kuat lain untuk integrasi SIAKAD ↔ modul SPMI ↔ PD Dikti secara otomatis (bukan input manual berulang).

### 11.5 Indikator Kinerja Utama (IKU) 2026
Kepmendiktisaintek No. 358/M/KEP/2025 memperluas IKU dari 8 menjadi **12 poin**, terbagi: **6 IKU Wajib**, **2 IKU Pilihan**, **1 IKU Partisipatif** (sisanya bersyarat tergantung jenis PT/status BLU-Satker-PTS). Cakupannya diperluas ke: efisiensi masa studi, keberhasilan lulusan, prestasi mahasiswa, reputasi internasional dosen, kerja sama & hilirisasi bermitra industri, pemanfaatan keilmuan kampus untuk kebijakan publik, kemandirian pendapatan, tata kelola bersih, keamanan-kesejahteraan sivitas akademika, dan kesejahteraan dosen. Karena rincian pastinya bisa bervariasi antar-sumber dan sedang dalam masa sosialisasi, sebaiknya modul SIAKAD dirancang dengan **struktur indikator yang fleksibel/configurable**, bukan hardcode 12 poin, agar mudah disesuaikan begitu Kemdiktisaintek merilis pedoman teknis final.

### 11.6 Alur Data LED/LKPS
```
Data akademik harian (SIAKAD)
        │
        ▼
GKM Prodi ── verifikasi ──► GPM Fakultas ── agregasi ──► LPMI
        │                                                    │
        ▼                                                    ▼
   Bukti evidence PPEPP                          Kompilasi LED (naratif)
   (AMI, monev, survei)                          + LKPS (data kuantitatif)
        │                                                    │
        └──────────────────► SUBMIT KE LAM/BAN-PT ◄──────────┘
```

Poin kritis: LKPS (data kuantitatif) idealnya **ditarik otomatis** dari basis data SIAKAD/PD Dikti, sedangkan LED (naratif evaluasi diri) tetap butuh penyusunan manusia — tapi argumentasi naratifnya harus **konsisten** dengan angka LKPS. Kontradiksi data yang Anda temukan di LED PTI kemungkinan besar terjadi karena LED disusun terpisah dari sumber data LKPS/SIAKAD, bukan ditarik dari sumber yang sama.

---

## 12. KALENDER/PERIODISASI MUTU TAHUNAN (Contoh Siklus Lengkap)

| Periode | Kegiatan | Tahap PPEPP |
|---|---|---|
| **Agustus–September** (awal TA baru) | Rapat kerja tahunan, penetapan/revisi target mutu & IKU tahun berjalan | Penetapan (lanjutan) |
| **September–Januari** (semester ganjil) | Pelaksanaan pembelajaran & standar; Monev tengah semester (Oktober/November); Monev akhir semester + survei kepuasan (Desember/Januari) | Pelaksanaan + Evaluasi (monev) |
| **Februari–Juli** (semester genap) | Pelaksanaan berlanjut; Monev tengah semester (Maret/April); Evaluasi capaian pembelajaran lulusan saat yudisium; Tracer study lulusan (umumnya 1x/tahun, untuk lulusan 1–2 tahun sebelumnya) | Pelaksanaan + Evaluasi |
| **Mei–Juni** | Perencanaan & penjadwalan AMI tahunan | Persiapan Evaluasi formal |
| **Juni–Juli** | Pelaksanaan AMI (opening → desk eval → visitasi → closing → LHA) | Evaluasi (formal/AMI) |
| **Juli–Agustus** | Penyusunan RTL oleh unit teraudit, verifikasi closing oleh LPMI | Pengendalian |
| **Agustus** (sebelum TA baru) | Rapat Tinjauan Manajemen (RTM) tingkat universitas & fakultas | Peningkatan |
| **Sesuai jadwal LAM/BAN-PT** (bukan tahunan, mengikuti siklus akreditasi prodi/PT) | Penyusunan & submisi LED/LKPS | Integrasi ke SPME |

**Catatan:** siklus PPEPP penuh (revisi standar besar) umumnya mengikuti periode Rencana Strategis (Renstra) 4–5 tahunan, sedangkan monitoring-evaluasi rutin berjalan tiap semester, dan AMI formal berjalan tahunan. Ketiga lapis periodisasi ini **berjalan paralel, bukan bergantian** — penting untuk desain sistem agar tidak menyamaratakan semua aktivitas mutu ke satu jenis "siklus".

---

## 13. MATRIKS PERAN & TANGGUNG JAWAB (RACI)

| Aktivitas | LPMI | Dekan/GPM | Kaprodi/GKM | Auditor | Rektor/Senat |
|---|---|---|---|---|---|
| Merumuskan Standar | R/A | C | C | I | A (pengesahan) |
| Menjalankan standar harian | I | A | R | I | I |
| Monev pembelajaran | C | A | R | I | I |
| Menjadwalkan AMI | R/A | I | I | I | I |
| Melaksanakan audit | A | I | I | R | I |
| Menyusun RTL | C | A | R | I | I |
| Verifikasi closing temuan | R/A | I | C | I | I |
| Memimpin RTM | C | I | I | I | R/A |
| Menyusun LED/LKPS | C/A | C | R | I | I |
| Submit ke LAM/BAN-PT | C | I | R | I | A |

*R = Responsible (pelaksana), A = Accountable (penanggung jawab akhir), C = Consulted (dimintai masukan), I = Informed (diberi tahu hasilnya)*

---

## 14. REKOMENDASI ARSITEKTUR MODUL e-SPMI UNTUK SIAKAD

Bagian ini menerjemahkan seluruh kerangka di atas menjadi blueprint fungsional, disesuaikan dengan stack yang biasa Anda pakai (Laravel + Livewire + Tailwind).

### 14.1 Peta Modul
| Modul | Fungsi | Terhubung ke |
|---|---|---|
| **M1 — Manajemen Dokumen Mutu** | Repositori Kebijakan/Manual/Standar/Formulir dengan versioning & alur approval (draft → review LPMI → pertimbangan Senat → SK Rektor) | M2, M7 |
| **M2 — Perumusan & Penetapan Standar** | Builder rumusan ABCD, target indikator, mapping ke SN Dikti (Luaran/Proses/Masukan/Penelitian/PkM) + penanda "melampaui SN Dikti" | M1, M3 |
| **M3 — Pelaksanaan & Evidence** | Upload bukti pelaksanaan per unit/prodi/periode, linked ke standar terkait | M2, M6 |
| **M4 — Monev & Survei** | Kuesioner terjadwal otomatis (kepuasan mahasiswa/dosen/tendik/pengguna lulusan/mitra), agregasi hasil real-time | M6 |
| **M5 — Audit Mutu Internal (AMI)** | Penjadwalan, penunjukan auditor (dengan validasi independensi otomatis: auditor ≠ unit sendiri), checklist audit digital, input temuan (KTS Mayor/Minor/OB/OFI), generate LHA | M3, M6 |
| **M6 — Pengendalian (RTL Tracker)** | Kanban/tracker RTL per temuan: PIC, tenggat, status (open/in-progress/closed), notifikasi otomatis mendekati deadline | M5, M7 |
| **M7 — RTM & Peningkatan** | Agenda builder, notulen digital, action item tracker dengan PIC & due date, riwayat keputusan | M6, M2 (siklus balik) |
| **M8 — Data Akreditasi (LED/LKPS)** | Generator draf LKPS otomatis dari data SIAKAD (jumlah dosen, rasio, IPK, masa studi dll), workspace kolaboratif penyusunan LED naratif dengan validasi silang ke angka LKPS (mencegah kontradiksi data) | M3, M4, integrasi PD Dikti |
| **M9 — Dashboard Eksekutif** | Traffic-light per standar/prodi/fakultas, radar chart capaian IKU (12 poin, configurable), drilldown sampai bukti evidence | Semua modul |
| **M10 — Notifikasi & Kalender Mutu** | Reminder otomatis sesuai kalender di Bab 12 (jadwal monev, AMI, RTM, deadline RTL) | Semua modul |

### 14.2 Entitas Data Inti (Konseptual, siap diturunkan jadi skema)
```
units (id, nama, tipe[universitas|fakultas|prodi|unit_pendukung], parent_id)
standards (id, kode, nama, kategori[luaran|proses|masukan|penelitian|pkm|non_akademik],
           rumusan_abcd, target_indikator, status_melampaui_sn_dikti, sk_penetapan_id, versi)
standard_periods (id, standard_id, tahun_akademik, target_capaian)
evidences (id, standard_id, unit_id, periode, file_path, uploaded_by, verified_by, status)
surveys (id, jenis[mahasiswa|dosen|tendik|pengguna_lulusan|mitra], periode, template_id)
survey_responses (id, survey_id, responden_ref, jawaban_json, submitted_at)
audit_schedules (id, unit_id, periode, tanggal_mulai, tanggal_selesai, status)
audit_assignments (id, audit_schedule_id, auditor_id, unit_diaudit_id) -- validasi auditor≠unit sendiri
audit_findings (id, audit_schedule_id, standard_id, kategori[kts_mayor|kts_minor|observasi|ofi],
                deskripsi, tanggal)
corrective_actions (id, finding_id, rtl_deskripsi, pic_user_id, tenggat, status, bukti_closing)
management_reviews (id, unit_id, tanggal, notulen, tahun_akademik)
review_action_items (id, management_review_id, deskripsi, pic_user_id, tenggat, status)
accreditation_docs (id, unit_id, jenis[led|lkps], lam_atau_banpt, status, file_path, tanggal_submit)
iku_indicators (id, kode, nama, sifat[wajib|pilihan|partisipatif], tahun_berlaku)
iku_achievements (id, iku_indicator_id, unit_id, periode, nilai_capaian, nilai_target)
```

### 14.3 Alur Kerja (Workflow) Kunci
1. **Alur Penetapan Standar:** GKM/GPM usul → LPMI review teknis → Senat beri pertimbangan (approval step di sistem, bisa berupa upload berita acara) → Rektor terbitkan SK (upload SK, status standar berubah "aktif") → standar terkunci untuk periode berjalan, revisi berikutnya hanya lewat siklus RTM.
2. **Alur AMI:** LPMI buat jadwal → sistem otomatis menyarankan pool auditor yang **valid** (bukan dari unit yang sama) → auditor input temuan via form terstruktur (kategori wajib dipilih) → sistem otomatis generate PTK untuk tiap KTS → auditee input RTL → LPMI verifikasi & tutup temuan → LHA otomatis ter-generate dari data terstruktur (bukan diketik ulang manual — ini juga mengurangi risiko kontradiksi data).
3. **Alur RTM:** Sistem otomatis menyiapkan draf agenda berisi ringkasan hasil AMI + status RTL + capaian IKU periode berjalan (data ditarik otomatis dari M5, M6, M9) → notulen diinput saat rapat → action items otomatis jadi entri baru yang dipantau sampai closing, sekaligus memicu siklus baru di M2 jika ada keputusan revisi standar.
4. **Alur LED/LKPS:** LKPS ditarik otomatis dari data SIAKAD inti (data mahasiswa, dosen, nilai, dsb) sehingga selalu sinkron; modul LED menyediakan editor kolaboratif dengan **panel referensi silang** yang menampilkan angka LKPS terkait saat narasi ditulis, sehingga penyusun tidak bisa menuliskan klaim yang bertentangan dengan data tanpa melihat peringatan/warning otomatis.

### 14.4 Kontrol Akses (Role-Based)
| Role | Akses |
|---|---|
| Admin LPMI Pusat | Semua modul, full CRUD standar, jadwal AMI, approval dokumen |
| Admin GPM Fakultas | Modul M3, M4, M8 (scope fakultas), read-only M2/M9 untuk unit sendiri |
| Admin GKM Prodi | Modul M3, M4, M8 (scope prodi sendiri), input evidence |
| Auditor | Modul M5 (scope sesuai penugasan saja, tidak bisa lihat unit lain di luar penugasan) |
| Pimpinan (Rektor/Dekan) | Dashboard M9 (read-only, semua scope), M7 (RTM) |
| Dosen/Tendik | Submit evidence terbatas ke standar yang relevan dengan tugasnya |

### 14.5 Prioritas Implementasi yang Disarankan
Mengingat urgensi LED LAMDIK PTI yang sedang berjalan, urutan pembangunan yang paling memberi dampak cepat:
1. **M8 (Data Akreditasi)** dulu — supaya LED yang sedang disusun langsung punya "sumber kebenaran tunggal" dan kontradiksi data ke depan bisa dicegah otomatis.
2. **M3 + M6 (Evidence + RTL Tracker)** — dasar untuk semua modul lain, dan langsung menyelesaikan masalah tabel DKPS kosong yang sudah teridentifikasi.
3. **M5 (AMI)** dan **M7 (RTM)** — untuk siklus rutin ke depan.
4. **M2, M4, M9, M10** — penyempurnaan setelah fondasi berjalan.

---

## 15. DAFTAR ISTILAH

| Istilah | Kepanjangan/Arti |
|---|---|
| LPMI/LPM/BPM | Lembaga/Badan Penjaminan Mutu (Internal) — unit pusat tingkat universitas |
| GPM/UPM | Gugus/Unit Penjaminan Mutu tingkat Fakultas |
| GKM/UPPS | Gugus Kendali Mutu / Unit Pengelola Program Studi tingkat Prodi |
| PPEPP | Penetapan, Pelaksanaan, Evaluasi, Pengendalian, Peningkatan |
| SPMI | Sistem Penjaminan Mutu Internal |
| SPME | Sistem Penjaminan Mutu Eksternal (= Akreditasi) |
| SN Dikti | Standar Nasional Pendidikan Tinggi |
| PD Dikti | Pangkalan Data Pendidikan Tinggi |
| AMI | Audit Mutu Internal |
| RTM | Rapat Tinjauan Manajemen |
| RTL | Rencana Tindak Lanjut |
| PTK | Permintaan Tindakan Koreksi |
| KTS | Ketidaksesuaian (temuan audit) |
| OFI | *Opportunity for Improvement* |
| LED | Laporan Evaluasi Diri |
| LKPS | Laporan Kinerja Program Studi |
| IKU | Indikator Kinerja Utama |
| LAM | Lembaga Akreditasi Mandiri (mis. LAMDIK untuk rumpun kependidikan) |
| BAN-PT | Badan Akreditasi Nasional Perguruan Tinggi (akreditasi institusi) |

---

## 16. REFERENSI REGULASI

1. Undang-Undang No. 12 Tahun 2012 tentang Pendidikan Tinggi
2. Peraturan Menteri Pendidikan Tinggi, Sains, dan Teknologi No. 39 Tahun 2025 tentang Penjaminan Mutu Pendidikan Tinggi (berlaku 2 September 2025)
3. Peraturan Menteri Pendidikan Tinggi, Sains, dan Teknologi No. 10 Tahun 2026 tentang Perubahan atas Permendiktisaintek No. 39 Tahun 2025 (diundangkan 16 Juli 2026)
4. Keputusan Menteri Pendidikan Tinggi, Sains, dan Teknologi No. 358/M/KEP/2025 tentang Indikator Kinerja Utama Perguruan Tinggi dan LLDikti
5. *(Regulasi terdahulu, sudah tidak berlaku namun berguna sebagai referensi historis)*: Permenristekdikti No. 62 Tahun 2016; Permendikbud No. 3 & 5 Tahun 2020; Permendikbudristek No. 53 Tahun 2023

**Catatan kehati-hatian:** dokumen ini disusun berdasarkan pemahaman regulasi hingga Agustus 2026. Karena regulasi SPM Dikti di Indonesia terbukti cukup dinamis dalam 3 tahun terakhir (tiga kali perubahan besar), disarankan mengecek langsung salinan resmi Permendiktisaintek 39/2025 jo. 10/2026 di situs Kemdiktisaintek/JDIH sebelum menjadikan dokumen ini sebagai rujukan tunggal untuk keperluan legal-formal (SK, LED resmi, dsb).
