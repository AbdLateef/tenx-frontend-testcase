## Frontend Test case

### Komponen:
- Frontend / Browser (Dashboard): Dashboard yang ditampilkan di browser klien menggunakan teknologi WebSocket untuk menerima update data secara real-time tanpa perlu refresh halaman.
- Backend Server (API Gateway): Berfungsi sebagai perantara antara frontend dan backend, menangani permintaan API dan menyediakan endpoint WebSocket.
- Message Broker (RabbitMQ): Mengelola aliran data dari database utama dan mendistribusikannya ke cache database dan frontend secara efisien.
- Cache Database (Redis): Menyimpan data yang sering diakses untuk mengurangi beban pada database utama dan menyediakan akses cepat ke data real-time.
- Main Database (MySQL): Menyimpan data transaksi utama, yang tidak diakses langsung oleh dashboard untuk mengurangi beban.

### Alur Sistem:
- Frontend Dashboard menggunakan WebSocket untuk menerima update data secara real-time dari backend tanpa refresh halaman.
- Backend Server berkomunikasi dengan Message Broker yang mengelola dan mendistribusikan perubahan data dari Main Database ke Cache Database.
- Cache Database menyediakan data yang sering diakses dengan cepat, mengurangi beban pada Main Database dan memastikan data di Dashboard selalu up-to-date tanpa membebani server.

<Diagram terlampir dengan format gambar (JPG)>