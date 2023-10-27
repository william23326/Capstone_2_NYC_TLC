# Capstone_2_NYC_TLC

# Latar Belakang

Dalam dunia transportasi perkotaan, data perjalanan taksi dan limusin adalah sumber informasi yang berharga untuk memahami perilaku penumpang, efisiensi layanan, serta dampak kebijakan dan tarif pada mobilitas kota. Di kota New York, data tersebut dikumpulkan oleh penyedia layanan LPEP dan mencakup berbagai variabel terkait perjalanan seperti tanggal, waktu, lokasi, jumlah penumpang, jarak tempuh, tarif, dan banyak lagi.

Dalam rangka untuk memahami lebih dalam tentang aspek-aspek krusial dari sistem transportasi umum di New York, kita akan melakukan analisis yang tentang dataset ini guna menjadi suatu kebutuhan. Oleh karena itu, pernyataan masalah berikut dirumuskan:

# Pernyataan Masalah

Sebagai seorang data analyst yang sedang menganalisa perusahaan taxi, kita akan mencoba untuk menjawab pertanyaan **bagaimana karakteristik perjalanan taksi dan limusin di New York City dapat dianalisis untuk mendapatkan wawasan yang lebih dalam tentang preferensi penumpang, efektivitas operasional, serta dampak kebijakan tarif dan peraturan transportasi pada sistem transportasi perkotaan?**

# Kesimpulan dan Rekomendasi

**Kesimpulan**

Dari keseluruhan analisis yang telah dilakukan, berikut adalah kesimpulan yang dapat diambil tentang karakteristik New York City:
Data awal terdiri dari 68.211 baris data dengan 20 kolom. Setelah melalui proses data cleaning dan penambahan kolom, akhirnya dataset ini menjadi terdiri dari 65747 baris dan 30 kolom.

- Berdasarkan `trip_distance`:
1. Karakteristik Penumpang Terhadap Jarak

    Warga di New York cenderung lebih sering menggunakan taxi sebagai opsi utama apabila jarak tempuhnya pendek ±1-2 miles. Hal ini mungkin disebabkan apabila jaraknya jauh, warga di New York lebih memilih menggunakan alternatif lain contohnya seperti menggunakan bus atau kereta.

2. Karakteristik Penumpang Terhadap Jarak dan Jam per Harinya pada Weekday dan Weekend
    - Warga New York cenderung melakukan perjalanan yang jaraknya jauh di pagi hari pukul 4am - 6am di saat warga hendak bekerja.
    - Untuk perjalanan jarak pendek dan sedang cenderung terjadi di rentang pukul 6am - 4am. Puncak perjalan jarak yang ssedang biasanya terjadi di pukul 11am saat menuju jam makan siang.

- Berdasarkan `income` terhadap `RatecodeID`:
    - Top 3 Rata-rata `total_amount` ada di perjalanan ke Bandara JFK & Newark diikuti dengan perjalanan keluar New York City. Faktor yang paling memengaruhi `total_amount` untuk perjalanan ke bandara secara berurutan adalah `fare_amount`, `tip_amount`, dan `tolls_amount`.
<br><br>
- Berdasarkan `passenger_count` terhadap `tip_amount`:
    - Jumlah Penumpang yang terdiri dari 1 hingga 3 orang tidak memiliki perbedaan yang signifikan dalam memberikan tip. Sedangkan penumpang yang terdiri dari 4 hingga 5 orang cenderung lebih dermawan dalam memberikan tip yang besar.
<br><br>
- Berdasarkan `congestion_surcharge` & `tip_amount` terhadap `total_amount`:
    - Biaya tambahan `congestion_surcharge` hanya memberikan kontribusi kecil terhadap total biaya perjalanan dalam sehari.
    - Penumpang cenderung memberi tip lebih besar sebagai persentase dari `total_amount` perjalanan mereka pada sore hari menuju malam.
<br><br>
- Berdasarkan `trip_type` terhadap `tip_percentage`:
    - Perjalanan street-hail (diambil dari jalan) memiliki `tip_percentage` (persentase tip) yang jauh lebih tinggi dibandingkan dengan perjalanan dispatch (dijalankan/dispatched).
<br><br>
- Berdasarkan perilaku penumpang dalam memberikan tip:
    - Persentase tip yang diberikan oleh penumpang ternyata dipengaruhi oleh jam di hari weekday dan weekend. Persentase tip di weekday berpuncak jam 10 malam, tapi dari rentang jam 7 malam hingga 10 malam persentase tip yang diberikan juga cukup besar. Namun untuk weekend, puncaknya ada di jam 4 pagi dan dari rentang jam 10 pagi hingga 10 malam persentase tipnya moderat.
<br><br>
- Korelasi antar atribut
    - `total_amount` memiliki korelasi yang kuat terhadap `fare_amount`, `trip_distance`, dan `duration`. Berati semakin tinggi nilai `fare_amount`, `trip_distance`, dan `duration`, maka akan semakin tinggi juga nilai `total_amount`. `fare_amount` juga memiliki korelasi positif dengan `trip_distance` dan `duration`.
<br><br>
- Berdasarkan zona, dibagi menjadi 2:
    - **Jumlah perjalanan** terhadap **PULocationName dan DOLocationName**
        Jumlah perjalanan dari lokasi penjemputan paling banyak ada di East Harlem North, East Harlem South, Central Harlem, Morningside Heights, dan 4Forest Hills. Sedangkan, lokasi penurunan paling banyak di East Harlem South, East Harlem North, Upper East Side North, Central Harlem, Upper West Side North. Hal ini berbanding lurus dengan biaya hidup di Harlem yang biayanya 25% lebih rendah dibandingkan dengan biaya hidup di kota secara keseluruhan. Tingginya tingkat penjemputan dan penurunan di lokasi ini mungkin dikarenakan banyaknya populasi di daerah tersebut.
        
    - **Tip rata-rata** perjalanan terhadap **PULocationName dan DOLocationName**
        Penumpang yang dijemput dari Lenox Hill West, Times Sq/Theatre District, Flushing Meadows-Corona Park, Sunset Park East, dan Glendale cenderung memberikan tip yang lebih besar. Sebaliknya, tip yang lebih besar diberikan oleh penumpang yang turun di Breezy Point/Fort Tilden/Riis Beach, Newark Airport, JFK Airport, Battery Park, dan Kensington.Zona asal dan tujuan dapat memengaruhi besar tip. Beberapa zona mungkin lebih ramai dan padat, sehingga pengemudi mungkin mengalami kesulitan dalam perjalanan. Zona-zona ini mungkin termasuk Lenox Hill West dan Times Sq/Theatre District. Sebaliknya, tujuan seperti Newark Airport atau JFK Airport mungkin memiliki tarif tetap atau lebih tinggi, sehingga penumpang mungkin kurang bersedia memberikan tip tambahan.

**Rekomendasi**
1. Beberapa lokasi padat seperti di Lenox Hill West dan Times Sq/Theatre District, cenderung memberikan tip yang lebih besar, pengemudi taksi dapat mempertimbangkan untuk meningkatkan layanan dan kenyamanan di lokasi tersebut. Hal ini dapat mencakup peningkatan kebersihan kendaraan, pelayanan yang ramah, dan penanganan lalu lintas yang lebih baik.

2. Metode pembayaran paling banyak adalah pembayaran menggunakan kartu kredit, dan cenderung memberikaan tip yang lebih besar. Pengemudi taksi dapat sekalian mempromosikan penggunaan  kartu kredit sebagai metode untuk mendorong pendapatan tip yang lebih besar. 

3. Di analisis ini, kita dapat melihat bahwa persentase tip cenderung meningkat pada jam-jam tertentu dalam sehari, terutama di weekend. Pengemudi taksi dapat mempertimbangkan untuk aktif selama periode waktu ini untuk meningkatkan pendapatan mereka. Hal ini juga didukung dengan meningkatnya jumlah perjalanan pada jam-jam tertentu sehingga peluang pengemudi untuk mendapatkan tip yang besar bisa dikatakan cukup besar.

4. Pengemudi taksi mungkin dapat disebarkan lebih banyak di sekitaran lingkungan Harlem. Hal ini dikarenakan pada jumlah perjalanan pada lingkungan tersebut adalah yang paling banyak, maupun sebagai titik penjemputan atau titik penurunan penumpang. Ini juga berlaku untuk perjalanan yang RatecodeID nya 2, taksi juga dapat disebarkan di Bandara JFK atau Manhattan. Karena untuk perjalanan dari Bandara JFK ke Manhattan atau sebaliknya, fare amountnya sudah dipatok $70 dan ini belum termasuk biaya-biaya lain. Penumpang yang turun di Bandara Newark dan JFK juga cenderung memberikan tip rata-rata yang cukup tinggi, Mungkin ini bisa jadi salah satu pertimbangan.

Analisis data ini diharapkan dapat memberikan wawasan yang mendalam tentang dinamika transportasi perkotaan di New York City, dan hasilnya dapat digunakan untuk pengambilan keputusan yang lebih baik dalam pengelolaan sistem transportasi, penyesuaian tarif, serta perencanaan perkotaan yang lebih efisien.
