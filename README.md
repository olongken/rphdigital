<!DOCTYPE html>
<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Platform RPH Digital</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 20px; }
        label, input, select, textarea { display: block; margin-top: 10px; width: 100%; }
        button { margin-top: 20px; padding: 10px; background: #4CAF50; color: white; border: none; cursor: pointer; }
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
            <option value="Pengenalan Seni dan Budaya">Pengenalan Seni dan Budaya</option>
            <option value="Prinsip Reka Bentuk">Prinsip Reka Bentuk</option>
            <option value="Teknik Lukisan dan Catan">Teknik Lukisan dan Catan</option>
            <option value="Seni Cetakan dan Arca">Seni Cetakan dan Arca</option>
            <option value="Reka Bentuk Grafik dan Digital">Reka Bentuk Grafik dan Digital</option>
        </select>
        
        <label>Objektif Pembelajaran:</label>
        <textarea id="objektif" rows="3" required></textarea>
        
        <label>Aktiviti Pembelajaran:</label>
        <textarea id="aktiviti" rows="3" required></textarea>
        
        <label>Refleksi Pengajaran:</label>
        <textarea id="refleksi" rows="3"></textarea>
        
        <button type="submit">Simpan RPH</button>
        <button type="button" onclick="exportToPDF()">Muat Turun PDF</button>
    </form>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.4.0/jspdf.umd.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf-autotable/3.5.23/jspdf.plugin.autotable.min.js"></script>
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
            
            doc.text("Rancangan Pengajaran Harian (RPH)", 10, 10);
            
            doc.autoTable({
                startY: 20,
                head: [['Maklumat', 'Perincian']],
                body: [
                    ['Nama Guru', namaGuru],
                    ['Nama Kelas', namaKelas],
                    ['Tarikh', tarikh],
                    ['Tajuk', tajuk],
                    ['Objektif Pembelajaran', objektif],
                    ['Aktiviti Pembelajaran', aktiviti],
                    ['Refleksi Pengajaran', refleksi]
                ],
                theme: 'grid'
            });
            
            doc.save('RPH_Seni_Visual.pdf');
        }
    </script>
</body>
</html>
