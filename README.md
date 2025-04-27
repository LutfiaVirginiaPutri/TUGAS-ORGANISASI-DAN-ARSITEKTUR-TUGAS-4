NAMA: LUTFIA VIRGINIA PUTRI

NIM:09011382328139

KELAS: SKU 2A

# PIPELINE-PROCESSING
# Pengertian-Pipeline-Processing

Dalam dunia komputer, pipeline adalah sekumpulan tahap pemrosesan data yang dihubungkan berurutan, di mana output dari satu tahap langsung menjadi input untuk tahap berikutnya. Biasanya, tahapan-tahapan ini bisa bekerja bersamaan (paralel), sehingga mempercepat pemrosesan keseluruhan.
Pipeline memungkinkan proses berjalan lebih efisien karena beberapa langkah bisa dikerjakan dalam waktu yang hampir bersamaan, masing-masing fokus pada tugasnya sendiri.

Contoh Pipeline di Komputer: 

- Pipeline Instruksi
Digunakan di prosesor (CPU) untuk mengeksekusi beberapa instruksi secara serentak dalam satu jalur digital. Pipeline ini membagi eksekusi instruksi menjadi beberapa langkah seperti pengambilan instruksi, penerjemahan (decode), penghitungan aritmatika, dan pengambilan data dari register. Setiap langkah menangani bagian dari instruksi yang berbeda pada waktu yang sama.

- Pipeline Grafis
Biasa ada di kartu grafis (GPU), di mana terdapat banyak unit perhitungan yang menangani berbagai tahap proses rendering, seperti transformasi perspektif, perhitungan pencahayaan, pewarnaan, hingga menggambar bentuk (primitives). Setiap tahapan bertugas mengolah bagian tertentu dari gambar.

- Pipeline Perangkat Lunak
Pada pipeline software, data yang dihasilkan dari satu program langsung diteruskan ke program lain untuk diproses lebih lanjut. Ini umum digunakan dalam pemrosesan data atau di sistem operasi berbasis Unix/Linux dengan penggunaan command line (misalnya menggunakan tanda |/pipe).

# Intruksi-Pipeline

Instruksi pipeline adalah teknik dalam prosesor di mana eksekusi sebuah instruksi dibagi ke dalam beberapa tahapan, dan tahapan-tahapan ini bekerja secara berurutan namun paralel untuk berbagai instruksi. Proses dimulai dengan mengambil instruksi dari memori dan menyimpannya ke dalam buffer. Setelah tahap selanjutnya siap, instruksi yang telah dibuffer tersebut dikirim untuk diproses lebih lanjut. Ketika instruksi pertama sedang diproses di tahap decode, tahap fetch memanfaatkan waktu yang ada untuk mengambil dan membuffer instruksi berikutnya, sehingga pipeline tetap terisi dan prosesor bekerja lebih efisien.

Dalam pipeline, karena tiap tahap menggunakan bagian berbeda dari CPU, beberapa instruksi bisa diproses secara bersamaan di tahapan yang berbeda. Sebagai contoh, saat instruksi pertama seperti ADD AX, AX diambil dari memori (Fetch), bagian decoding (Decode) masih belum digunakan. Setelah itu, saat instruksi pertama diterjemahkan di tahap Decode, tahap Fetch sudah bisa mengambil instruksi kedua seperti ADD EX, CX. Proses ini berlanjut, di mana saat instruksi pertama dieksekusi (Execute), instruksi kedua diterjemahkan (Decode), dan instruksi ketiga bisa mulai diambil (Fetch). Dengan sistem pipeline, pemrosesan instruksi menjadi lebih cepat karena meminimalkan waktu tunggu antar bagian prosesor, membuat semua komponen bekerja lebih optimal dan simultan.

# Contoh-Kasus-Pipeline-Processing

Salah satu contoh penggunaan pipeline processing dalam sistem keamanan modern adalah proses deteksi dan pengenalan wajah secara real-time dari video kamera pengawas di bandara. Proses ini dimulai dengan pengambilan data berupa aliran video dari kamera IP, yang kemudian dibagi menjadi potongan-potongan gambar (frame) berdasarkan interval waktu tertentu. Setiap frame ini kemudian melewati tahapan awal seperti perubahan ukuran gambar (resize), penyesuaian warna (jika diperlukan), dan normalisasi nilai piksel agar data sesuai dengan standar input model kecerdasan buatan.

Setelah pra-pemrosesan, sistem masuk ke tahap deteksi wajah menggunakan algoritma berbasis convolutional neural networks (CNN), seperti MTCNN atau YOLO, untuk menemukan dan menandai posisi wajah dalam setiap frame. Wajah-wajah yang berhasil dideteksi kemudian diproses lebih lanjut di tahap pengenalan wajah, di mana sistem melakukan ekstraksi ciri-ciri khusus wajah dan mengubahnya menjadi representasi numerik (embedding), menggunakan model seperti FaceNet. Representasi ini dibandingkan dengan data identitas yang sudah tersimpan di database. Jika sistem tidak menemukan kecocokan dengan data yang ada, individu tersebut akan ditandai sebagai orang asing dan dikategorikan sebagai potensi ancaman.

Selanjutnya, hasil dari proses ini diteruskan ke sistem logging dan notifikasi, yang akan mencatat aktivitas tersebut dan mengirimkan peringatan otomatis ke petugas keamanan bila ditemukan aktivitas mencurigakan di area yang diawasi. Dengan pipeline processing, seluruh alur ini berjalan secara berurutan dan efisien, memungkinkan sistem memberikan respons cepat dan akurat di lingkungan yang membutuhkan reaksi waktu nyata.
