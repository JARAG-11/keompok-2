<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kelompok Kami</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        body {
            font-family: 'Roboto', sans-serif;
            margin: 0;
            padding: 0;
            background: #f5f5f5;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* Sidebar */
        .sidebar {
            width: 240px;
            background-color: #333;
            color: white;
            position: fixed;
            top: 0;
            bottom: 0;
            left: 0;
            padding-top: 50px;
            box-shadow: 2px 0 5px rgba(0, 0, 0, 0.2);
            z-index: 100;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .sidebar a {
            padding: 15px 20px;
            text-decoration: none;
            color: white;
            display: block;
            width: 100%;
            text-align: center;
            font-size: 1.2em;
            margin-bottom: 20px;
            font-weight: 700;
            border-radius: 5px;
            transition: all 0.3s ease;
        }

        .sidebar a:hover {
            background-color: #4CAF50;
            color: white;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }

        .home {
            background-color: #FF5722;
            font-weight: 700;
            font-size: 1.5em;
            margin-bottom: 50px;
        }

        .home:hover {
            background-color: #e64a19;
        }

        .profile-link {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-top: 10px;
        }

        .profile-link a {
            font-size: 1.1em;
            color: white;
            transition: color 0.3s ease;
        }

        .profile-link a:hover {
            color: #FFEB3B;
        }

        .content {
            margin-left: 240px;
            padding: 40px;
            width: calc(100% - 240px);
            background: #fff;
            min-height: 100vh;
        }

        header {
            text-align: center;
            padding: 50px 0;
            background-color: #4CAF50;
            color: white;
            margin-bottom: 30px;
            font-size: 2.5em;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }

        .profile {
            display: none;
            text-align: center;
            transition: opacity 0.4s ease;
            margin-top: 30px;
            opacity: 0;
        }

        .profile.active {
            display: block;
            opacity: 1;
        }

        .section-title {
            font-size: 2.5em;
            color: #333;
            margin-bottom: 20px;
            text-align: center;
            font-weight: 700;
        }

        footer {
            text-align: center;
            padding: 20px;
            background-color: #333;
            color: white;
            width: 100%;
            position: fixed;
            bottom: 0;
            left: 0;
        }

        /* Galeri Foto */
        .gallery {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .gallery img {
            width: 300px;
            height: 300px;
            object-fit: cover;
            border-radius: 10px;
            transition: transform 0.3s ease;
        }

        .gallery img:hover {
            transform: scale(1.1);
        }

        /* Formulir Kontak */
        .contact-form {
            background: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
            margin: 30px auto;
            max-width: 600px;
            width: 100%;
        }

        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        .contact-form button {
            background: #4CAF50;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .contact-form button:hover {
            background-color: #45a049;
        }

        /* Testimonial */
        .testimonials {
            margin-top: 50px;
            display: flex;
            justify-content: space-evenly;
            flex-wrap: wrap;
        }

        .testimonial {
            background-color: #fff;
            border-radius: 10px;
            padding: 25px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
            width: 250px;
            text-align: center;
            margin-bottom: 20px;
            transition: transform 0.3s ease;
        }

        .testimonial:hover {
            transform: scale(1.05);
        }

        .testimonial p {
            font-style: italic;
            color: #666;
            font-size: 1.1em;
        }

        .testimonial h4 {
            font-size: 1.3em;
            margin-top: 15px;
            color: #333;
        }

        /* FAQ */
        .faq {
            margin-top: 50px;
        }

        .faq h2 {
            font-size: 2.5em;
            margin-bottom: 20px;
            text-align: center;
        }

        .faq-item {
            margin-bottom: 15px;
            background: #fff;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        .faq-item h3 {
            margin: 0;
            font-size: 1.6em;
            color: #333;
        }

        .faq-item p {
            font-size: 1em;
            color: #555;
            margin-top: 10px;
        }

        /* Animasi Scroll */
        .fade-in {
            opacity: 0;
            animation: fadeIn 1s forwards;
        }

        @keyframes fadeIn {
            to {
                opacity: 1;
            }
        }

        @media (max-width: 768px) {
            .sidebar {
                width: 100%;
                height: auto;
                position: relative;
                padding-top: 20px;
            }

            .content {
                margin-left: 0;
                padding: 20px;
            }

            .gallery img {
                width: 100%;
                max-width: 300px;
                margin-bottom: 20px;
            }

            .testimonials {
                flex-direction: column;
                align-items: center;
            }

            .testimonial {
                width: 90%;
                margin-bottom: 30px;
            }
        }
    </style>
</head>
<body>

<!-- Sidebar Menu -->
<div class="sidebar">
    <a href="#" class="home">Home</a>
    <a href="#rasya" id="rasya-link">Javier</a>
    <a href="#reifan" id="reifan-link">Reifan</a>
    <a href="#pradita" id="pradita-link">Pradita</a>
    <a href="#azriel" id="azriel-link">Azriel</a>
    <a href="#arya" id="arya-link">Galuh</a>
    <a href="#contact">Contact Us</a>
    <a href="#gallery">Gallery</a>
    <a href="#testimonials">Testimonials</a>
    <a href="#faq">FAQ</a>
</div>

<!-- Main Content -->
<div class="content">
    <header class="fade-in">
        <h1>Selamat Datang di Website Kelompok Kami</h1>
        <p>Kenali anggotanya dengan mengklik nama!</p>
    </header>

    <!-- Profil Anggota -->
    <section id="rasya" class="profile fade-in">
        <h2>Muhammad Rasya Javier</h2>
		<p>Lahir: Banyumas,7 April 2007</p>
        <p>Alamat:Sukamanah 2 Blok A5 No.24 </p>
		<p>Hobi: bermain gitar, Menulis puisi, Menggambar</p>
        <p>No Telp: 089542499933</p>
        <p>Rasya adalah anggota yang memiliki keahlian dalam pengembangan perangkat lunak dan analisis sistem.</p>
		<p>Dia sangat berfokus pada penyelesaian masalah teknis yang kompleks dan memberikan solusi kreatif.</p>		
    </section>

    <section id="reifan" class="profile fade-in">
        <h2>Muhammad Reifan Akbar</h2>
        <p>Lahir: Jepara,3 Januari 2008</p>
        <p>Alamat: Perumahan Sutera Mediterania Blok C.6</p>
		<p>Hobi: Renang, Futsal, Sepak Bola</p>
        <p>No Telp: 089662142577</p>
		<p>Status: Pelajar</p>
		<p>Alamat Sekolah: SMK Mutiara Insan Nusantara
		<p>Jurusan: Teknik Komputer Jaringan
		<p>Reifan adalah anggota yang ahli dalam desain grafis dan pengalaman pengguna (UX).</p>
		<p>Ia bertanggung jawab dalam menciptakan desain antarmuka yang ramah pengguna dan visual yang menarik.</p>
    </section>

    <section id="pradita" class="profile fade-in">
        <h2>Pradita Widiantara</h2>
		<p>Lahir: Tangerang,6 Agustus 2008</p>
        <p>Alamat: Kampung Pandan Indah</p>
		<p>Hobi: Renang, Futsal, Sepak Bola</p>
        <p>No Telp: 085782582307</p>
		<p>Status: Pelajar</p>
		<p>Alamat Sekolah: SMK Mutiara Insan Nusantara
		<p>Jurusan: Teknik Komputer Jaringan
        <p>Pradita memiliki latar belakang di bidang manajemen proyek dan komunikasi. Dia berperan dalam mengatur proyek dan memastikan setiap anggota kelompok bekerja sesuai rencana.</p>
    </section>

    <section id="azriel" class="profile fade-in">
        <h2>Muhammad Azriel Satria Prabowo</h2>
		<p>Lahir: Bekasi, 5 April 2008</p>
        <p>Alamat: Gardenia Residence Blok E4 No 6</p>
		<p>Hobi: Main Yoyo</p>
        <p>No Telp: 087819045178</p>
		<p>Status: Pelajar</p>
		<p>Alamat Sekolah: SMK Mutiara Insan Nusantara
		<p>Jurusan: Teknik Komputer Jaringan
        <p>Azriel adalah ahli di bidang analisis data dan kecerdasan buatan. Ia bertanggung jawab dalam membuat prediksi dan analisis yang mendalam untuk mendukung keputusan bisnis.</p>
    </section>

    <section id="arya" class="profile fade-in">
        <h2>Arya Galuh</h2>
		<p>Lahir: Jakarta, 7 April 2007</p>
        <p>Alamat: Neo Rajeg City Blok G5</p>
		<p>Hobi: Main Gitar</p>
        <p>No Telp: 087850602355</p>
		<p>Status: Pelajar</p>
		<p>Alamat Sekolah: SMK Mutiara Insan Nusantara
		<p>Jurusan: Teknik Komputer Jaringan
        <p>Arya adalah seorang pengembang web dan aplikasi yang sangat terampil. Dia memiliki kemampuan dalam berbagai bahasa pemrograman dan berkontribusi dalam pengembangan website dan aplikasi kelompok kami.</p>
    </section>

    <!-- Galeri Foto -->
    <section id="gallery" class="fade-in">
        <h2 class="section-title">Galeri Kami</h2>
        <div class="gallery">
            <img src="FOTO REIFAN.jpeg" alt="Gallery 1">
            <img src="FOTO PRADITA.jpeg" alt="Gallery 2">
            <img src="FOTO JEPRI.jpeg" alt="Gallery 3">
			<img src="FOTO AZRIEL.jpeg" alt="Gallery 4">
			<img src="FOTO GALUH.jpeg" alt="Gallery 5">
        </div>
    </section>

    <!-- Formulir Kontak -->
    <section id="contact" class="fade-in">
        <h2 class="section-title">Kontak Kami</h2>
        <form class="contact-form">
            <input type="text" placeholder="Nama" required>
            <input type="email" placeholder="Email" required>
            <textarea placeholder="Pesan" required></textarea>
            <button type="submit">Kirim Pesan</button>
        </form>
    </section>

    <!-- Testimonial -->
    <section id="testimonials" class="fade-in">
        <h2 class="section-title">Testimonial Anggota</h2>
        <div class="testimonials">
            <div class="testimonial">
                <p>"Kelompok kami selalu bekerja dengan semangat dan kekompakan yang luar biasa!"</p>
                <h4>- Muhammad Rasya Javier</h4>
            </div>
            <div class="testimonial">
                <p>"Proyek yang kami lakukan selalu penuh tantangan dan pembelajaran baru."</p>
                <h4>- Pradita Widiantara</h4>
            </div>
        </div>
    </section>

    <!-- FAQ -->
    <section id="faq" class="fade-in">
        <h2 class="section-title">Frequently Asked Questions</h2>
        <div class="faq-item">
            <h3>Apa tujuan kelompok ini?</h3>
            <p>Kelompok ini bertujuan untuk membangun proyek yang bermanfaat bagi kalangan siswa.</p>
        </div>
        <div class="faq-item">
            <h3>Bagaimana cara bergabung dengan kelompok?</h3>
            <p>Kami menerima anggota yang memiliki minat dan semangat yang tinggi dalam bidang yang kami geluti.</p>
        </div>
    </section>

    <footer>
        <p>Kelompok 5 | Website Kelompok Kami</p>
    </footer>
</div>

<script>
    // Function to hide all profiles
    function hideAllProfiles() {
        const profiles = document.querySelectorAll('.profile');
        profiles.forEach(profile => {
            profile.classList.remove('active');
        });
    }

    // Add event listeners to each menu link
    document.getElementById('rasya-link').addEventListener('click', function() {
        hideAllProfiles();
        document.getElementById('rasya').classList.add('active');
    });

    document.getElementById('reifan-link').addEventListener('click', function() {
        hideAllProfiles();
        document.getElementById('reifan').classList.add('active');
    });

    document.getElementById('pradita-link').addEventListener('click', function() {
        hideAllProfiles();
        document.getElementById('pradita').classList.add('active');
    });

    document.getElementById('azriel-link').addEventListener('click', function() {
        hideAllProfiles();
        document.getElementById('azriel').classList.add('active');
    });
    
    document.getElementById('arya-link').addEventListener('click', function() {
        hideAllProfiles();
        document.getElementById('arya').classList.add('active');
    });
</script>

</body>
</html>
