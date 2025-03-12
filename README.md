<!DOCTYPE html>
<html>
<head>
    <title>Memproses Scan...</title>
    <script>
        window.onload = function() {
            // Ambil nama pengguna (jika ada login, bisa diganti dengan data dari database)
            var nama = localStorage.getItem("namaPengguna") || "Anonim";
            
            // Ambil informasi perangkat dari browser
            var userAgent = navigator.userAgent;

            // URL Google Apps Script Web App (GANTI dengan URL Web App Anda)
            var webAppURL = "https://script.google.com/macros/s/AKfycbwb0xP18G3ahG3gvFyFYCXE78D9FGOEjk9Uttt8_6xR5Ixl0t1UdhgrT6Cc5eYO-nrH/exec";

            // Buat URL dengan parameter
            var targetURL = webAppURL + "?nama=" + encodeURIComponent(nama) + "&ua=" + encodeURIComponent(userAgent);

            // Debug: Tampilkan URL sebelum redirect (untuk memastikan data dikirim dengan benar)
            document.body.innerHTML = "<h3>Mengirim data...</h3><p><a href='" + targetURL + "'>Klik di sini jika tidak diarahkan otomatis</a></p>";

            // Arahkan pengguna ke Web App setelah 3 detik (agar bisa melihat URL yang dikirim)
            setTimeout(function() {
                window.location.href = targetURL;
            }, 3000);
        };
    </script>
</head>
<body>
    <h3>Sedang memproses data...</h3>
</body>
</html>
