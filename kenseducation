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
            <option value="Pengenalan jenis-jenis lukisan">Pengenalan jenis-jenis lukisan</option>
            <option value="Media dan teknik asas lukisan">Media dan teknik asas lukisan</option>
            <option value="Pengamatan satu objek">Pengamatan satu objek</option>
            <option value="Pengamatan antara objek">Pengamatan antara objek</option>
            <option value="Lukisan kajian sejadi dan buatan manusia">Lukisan kajian sejadi dan buatan manusia</option>
            <option value="Lukisan teknikal">Lukisan teknikal</option>
            <option value="Ilustrasi penerbitan dan industri">Ilustrasi penerbitan dan industri</option>
        </select>
        
        <label>Objektif Pembelajaran:</label>
        <textarea id="objektif" rows="3" required></textarea>
        <button type="button" onclick="dapatkanCadangan('objektif')">Cadangan ChatGPT</button>
        
        <label>Aktiviti Pembelajaran:</label>
        <textarea id="aktiviti" rows="3" required></textarea>
        <button type="button" onclick="dapatkanCadangan('aktiviti')">Cadangan ChatGPT</button>
        
        <label>Refleksi Pengajaran:</label>
        <textarea id="refleksi" rows="3"></textarea>
        <button type="button" onclick="dapatkanCadangan('refleksi')">Cadangan ChatGPT</button>
        
        <button type="submit">Simpan RPH</button>
        <button type="button" onclick="exportToWord()">Muat Turun Word</button>
    </form>

    <script>
        function dapatkanCadangan(id) {
            const contohCadangan = {
                "objektif": "1. Pelajar dapat mengenal pasti dan memahami asas tajuk yang diajar.\n2. Pelajar dapat mengaplikasikan teknik dan kemahiran dalam penghasilan karya seni.",
                "aktiviti": "1. Penerangan konsep dan teori oleh guru.\n2. Demonstrasi teknik oleh guru.\n3. Latihan amali oleh pelajar.",
                "refleksi": "1. Pelajar memahami dan dapat melaksanakan aktiviti dengan baik.\n2. Beberapa pelajar memerlukan bimbingan tambahan."
            };
            document.getElementById(id).value = contohCadangan[id];
        }
        
        function exportToWord() {
            const namaGuru = document.getElementById('namaGuru').value;
            const namaKelas = document.getElementById('namaKelas').value;
            const tarikh = document.getElementById('tarikh').value;
            const tajuk = document.getElementById('tajuk').value;
            const objektif = document.getElementById('objektif').value;
            const aktiviti = document.getElementById('aktiviti').value;
            const refleksi = document.getElementById('refleksi').value;
            
            let content = `\nRancangan Pengajaran Harian (RPH)\n\n` +
                          `Nama Guru: ${namaGuru}\nNama Kelas: ${namaKelas}\nTarikh: ${tarikh}\nTajuk: ${tajuk}\n\n` +
                          `| Kategori                | Kandungan |\n` +
                          `|------------------------|------------------------------------------------|\n` +
                          `| **Objektif**           | ${objektif.replace(/\n/g, ' ')} |\n` +
                          `| **Aktiviti**           | ${aktiviti.replace(/\n/g, ' ')} |\n` +
                          `| **Refleksi**           | ${refleksi.replace(/\n/g, ' ')} |\n`;
            
            const blob = new Blob([content], { type: 'application/msword' });
            const link = document.createElement('a');
            link.href = URL.createObjectURL(blob);
            link.download = 'RPH_Seni_Visual.doc';
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
        }
    </script>
</body>
</html>
