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
            <option value="Sejarah Seni dan Pengaruhnya">Sejarah Seni dan Pengaruhnya</option>
            <option value="Prinsip Reka Bentuk dan Estetika">Prinsip Reka Bentuk dan Estetika</option>
            <option value="Teknik dan Medium dalam Seni Visual">Teknik dan Medium dalam Seni Visual</option>
        </select>
        
        <label>Objektif Pembelajaran:</label>
        <textarea id="objektif" rows="3" required></textarea>
        
        <label>Aktiviti Pembelajaran:</label>
        <textarea id="aktiviti" rows="3" required></textarea>
        
        <label>Refleksi Pengajaran:</label>
        <textarea id="refleksi" rows="3"></textarea>
        
        <button type="submit">Simpan RPH</button>
        <button type="button" onclick="exportToWord()">Muat Turun Word</button>
    </form>

    <script>
        document.getElementById('rphForm').addEventListener('submit', function(event) {
            event.preventDefault();
            alert('RPH berjaya disimpan!');
        });
        
        function exportToWord() {
            let namaGuru = document.getElementById('namaGuru').value;
            let namaKelas = document.getElementById('namaKelas').value;
            let tarikh = document.getElementById('tarikh').value;
            let tajuk = document.getElementById('tajuk').value;
            let objektif = document.getElementById('objektif').value;
            let aktiviti = document.getElementById('aktiviti').value;
            let refleksi = document.getElementById('refleksi').value;
            
            let content = `\nRancangan Pengajaran Harian (RPH)\n\n` +
                          `Nama Guru: ${namaGuru}\n` +
                          `Nama Kelas: ${namaKelas}\n` +
                          `Tarikh: ${tarikh}\n` +
                          `Tajuk: ${tajuk}\n\n` +
                          `Objektif Pembelajaran:\n${objektif}\n\n` +
                          `Aktiviti Pembelajaran:\n${aktiviti}\n\n` +
                          `Refleksi Pengajaran:\n${refleksi}\n`;
            
            let blob = new Blob([content], { type: 'application/msword' });
            let link = document.createElement('a');
            link.href = URL.createObjectURL(blob);
            link.download = 'RPH_Seni_Visual.doc';
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
        }
    </script>
</body>
</html>
