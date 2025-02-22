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
    <h1>Platform RPH Digital - Seni Visual STPM</h1>
    <form id="rphForm">
        <label>Nama Guru:</label>
        <input type="text" id="namaGuru" required>
        
        <label>Nama Kelas:</label>
        <input type="text" id="namaKelas" required>
        
        <label>Tarikh:</label>
        <input type="date" id="tarikh" required>
        
        <label>Tajuk Pengajaran:</label>
        <select id="tajuk">
            <option value="Apresiasi Seni Visual">Apresiasi Seni Visual</option>
            <option value="Lukisan Pengkaryaan dan Perekaan">Lukisan Pengkaryaan dan Perekaan</option>
            <option value="Projek Kajian Seni Visual">Projek Kajian Seni Visual</option>
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
                objektif: "1. Pelajar dapat memahami konsep asas tajuk.\n2. Pelajar dapat mengaplikasikan teknik dalam penghasilan karya.",
                aktiviti: "1. Penerangan teori oleh guru.\n2. Demonstrasi teknik oleh guru.\n3. Pelajar menjalankan latihan amali.",
                refleksi: "1. Pelajar menunjukkan pemahaman yang baik dalam aktiviti.\n2. Beberapa pelajar memerlukan bimbingan tambahan."
            };
            document.getElementById(field).value = suggestions[field];
        }
    </script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.4.0/jspdf.umd.min.js"></script>
</body>
</html>
