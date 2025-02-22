<!DOCTYPE html>
<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Platform RPH Digital</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 20px; }
        label, input, select, textarea, button { display: block; margin-top: 10px; width: 100%; }
        button { padding: 10px; background: #4CAF50; color: white; border: none; cursor: pointer; }
        button:hover { background: #45a049; }
    </style>
</head>
<body>
    <h1>Platform RPH Digital - Seni Visual STPM (Penggal 2)</h1>
    <form id="rphForm">
        <label>Nama Guru:</label>
        <input type="text" id="namaGuru" required>
        
        <label>Nama Kelas:</label>
        <input type="text" id="namaKelas" required>
        
        <label>Tarikh:</label>
        <input type="date" id="tarikh" required>
        
        <label>Tajuk Pengajaran:</label>
        <select id="tajuk">
            <option value="Pengenalan Jenis-jenis Lukisan">Pengenalan Jenis-jenis Lukisan</option>
            <option value="Kemahiran Asas Lukisan">Kemahiran Asas Lukisan</option>
            <option value="Pengamatan - Satu Objek & Antara Objek">Pengamatan - Satu Objek & Antara Objek</option>
            <option value="Penggubahan Lukisan Kajian Sejadi dan Buatan Manusia">Penggubahan Lukisan Kajian Sejadi dan Buatan Manusia</option>
            <option value="Lukisan Teknikal">Lukisan Teknikal</option>
            <option value="Ilustrasi Penerbitan dan Industri">Ilustrasi Penerbitan dan Industri</option>
        </select>
        
        <label>Objektif Pembelajaran:</label>
        <textarea id="objektif" rows="3" required></textarea>
        <button type="button" onclick="generateSuggestion('objektif')">Dapatkan Cadangan</button>
        
        <label>Aktiviti Pembelajaran:</label>
        <textarea id="aktiviti" rows="3" required></textarea>
        <button type="button" onclick="generateSuggestion('aktiviti')">Dapatkan Cadangan</button>
        
        <label>Refleksi Pengajaran:</label>
        <textarea id="refleksi" rows="3"></textarea>
        <button type="button" onclick="generateSuggestion('refleksi')">Dapatkan Cadangan</button>
        
        <button type="submit">Simpan RPH</button>
        <button type="button" onclick="exportToPDF()">Muat Turun PDF</button>
    </form>

    <script>
        document.getElementById('rphForm').addEventListener('submit', function(event) {
            event.preventDefault();
            alert('RPH berjaya disimpan!');
        });
        
        function exportToPDF() {
            const { jsPDF } = window.jspdf;
            let doc = new jsPDF();
            
            let namaGuru = document.getElementById('namaGuru').value;
            let namaKelas = document.getElementById('namaKelas').value;
            let tarikh = document.getElementById('tarikh').value;
            let tajuk = document.getElementById('tajuk').value;
            let objektif = document.getElementById('objektif').value;
            let aktiviti = document.getElementById('aktiviti').value;
            let refleksi = document.getElementById('refleksi').value;
            
            doc.text(`Rancangan Pengajaran Harian (RPH)`, 10, 10);
            doc.text(`Nama Guru: ${namaGuru}`, 10, 20);
            doc.text(`Nama Kelas: ${namaKelas}`, 10, 30);
            doc.text(`Tarikh: ${tarikh}`, 10, 40);
            doc.text(`Tajuk: ${tajuk}`, 10, 50);
            doc.text(`Objektif: ${objektif}`, 10, 60);
            doc.text(`Aktiviti: ${aktiviti}`, 10, 70);
            doc.text(`Refleksi: ${refleksi}`, 10, 80);
            
            doc.save('RPH_Seni_Visual.pdf');
        }
        
        function generateSuggestion(field) {
            let suggestions = {
                objektif: "1. Pelajar dapat mengenal pasti dan memahami asas tajuk yang diajar.\n2. Pelajar dapat mengaplikasikan teknik dan kemahiran dalam penghasilan lukisan.",
                aktiviti: "1. Penerangan konsep dan teori oleh guru.\n2. Demonstrasi teknik oleh guru.\n3. Pelajar menjalankan latihan amali berdasarkan tajuk yang dipilih.",
                refleksi: "1. Pelajar menunjukkan pemahaman yang baik dalam aktiviti.\n2. Beberapa pelajar memerlukan bimbingan tambahan untuk menguasai teknik tertentu."
            };
            document.getElementById(field).value = suggestions[field];
        }
    </script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.4.0/jspdf.umd.min.js"></script>
</body>
</html>
