# Handoff: Dynamic Blog Homepage + Yoast Optimization
**Tanggal sesi:** 31 Mei 2026  
**Project:** onlineumkm.id  
**Sertakan di project:** Project utama onlineumkm.id  
**Referensi sebelumnya:** `onlineumkm-handoff.md`

---

## Ringkasan Sesi Ini

Tiga fokus utama sesi ini:
1. Otomasi section blog di homepage — tidak perlu edit manual setiap ada artikel baru
2. Fix waktu baca artikel yang tidak akurat di homepage
3. Optimasi Yoast SEO untuk halaman Blog dan Tentang Kami

---

## Changed (Sesi Ini)

| Item | Perubahan | Status |
|---|---|---|
| Blog section homepage | Diganti dari 3 kartu hardcoded ke dynamic fetch via WordPress REST API | ✅ Selesai |
| Fix waktu baca | Sebelumnya dihitung dari excerpt (tidak akurat), sekarang dari isi artikel penuh (200 kata/menit) | ✅ Selesai |
| Fix script rusak | Script duplikat menyebabkan semua tombol mati — dibersihkan dan diganti versi bersih | ✅ Selesai |
| Yoast — halaman Blog | Focus keyword, SEO title, meta description, slug diperbaiki | ✅ Selesai |
| Yoast — halaman Tentang Kami | Focus keyword, SEO title, meta description dioptimasi — 6 iterasi | ✅ Selesai |
| Konten bio Tentang Kami | Ditulis ulang — lebih profesional, hangat, ramah — tersedia 2 versi (panjang & ringkas) | ✅ Selesai |

---

## Current State — Yoast per Halaman

| Halaman | Focus Keyword | SEO Title | Meta Desc | Analisis SEO | Keterbacaan |
|---|---|---|---|---|---|
| Homepage | `jasa pembuatan website UMKM` | ✅ Hijau | ✅ Hijau | ✅ Hijau | 🔴 Merah |
| Blog `/blog/` | `tips SEO UMKM` | ✅ Hijau | ✅ Hijau | 🔴 Merah (normal — posts archive) | 🔴 Merah |
| Tentang Kami `/tentang/` | `jasa website UMKM` | ✅ Hijau | ✅ Hijau | 🟠 Oranye (4 merah, 11 hijau) | Belum dicek |

### Detail Yoast Tentang Kami — Masalah yang Tersisa

| Item | Status | Keterangan |
|---|---|---|
| Frasa kunci dalam atribut alt gambar | 🔴 Merah | Perlu upload foto + set alt text |
| Gambar | 🔴 Merah | Tidak ada gambar di halaman |
| Frasa kunci di awal | 🔴 Merah | Keyword di paragraf pertama — akan terselesaikan jika konten bio baru di-paste |
| Frasa kunci dalam subjudul | 🔴 Merah | Keyword belum ada di heading Elementor |
| Frasa kunci pada judul SEO | 🟠 Oranye | Tidak exact match — biarkan dulu |
| Kata kunci di slug | 🟠 Oranye | Slug `tentang` tidak ubah — akan break nav links |
| Tautan internal | ✅ Hijau | — |
| Kepadatan frasa kunci | ✅ Hijau | 4 kali |
| Meta description | ✅ Hijau | — |

### Catatan Blog Yoast Merah

Halaman Blog adalah **Posts Archive Page** — Yoast tidak bisa analisis konten dinamisnya. Analisis SEO merah di halaman arsip adalah **normal dan tidak bisa diperbaiki**. Yang penting (meta title + description) sudah hijau.

---

## Yoast Settings — Referensi Final

### Halaman Blog (`/blog/`)
```
Focus Keyword : tips SEO UMKM
SEO Title     : Blog Tips SEO & Promosi Online untuk UMKM | OnlineUMKM.id
Slug          : blog
Meta Desc     : Tips SEO, promosi online, dan digital marketing khusus UMKM
                Indonesia — panduan praktis ditulis dalam bahasa yang mudah
                dipahami.
```

### Halaman Tentang Kami (`/tentang/`)
```
Focus Keyword : jasa website UMKM
SEO Title     : Tentang OnlineUMKM.id | Jasa Website & SEO UMKM Medan
Slug          : tentang
Meta Desc     : OnlineUMKM.id adalah jasa website dan SEO lokal berbasis di
                Medan, melayani UMKM seluruh Indonesia. Kenali Ronald Huson
                dan misi kami.
```

---

## Konten Bio Tentang Kami — Versi Final

Dua versi tersedia. **Versi Ringkas direkomendasikan** untuk layout dua kolom.

### Versi Ringkas (5 paragraf — ±230 kata) ← GUNAKAN INI

```
Satu Keyakinan Sederhana

Nama saya Ronald Huson. Saya membangun OnlineUMKM.id — sebuah jasa website
UMKM berbasis di Medan — dari satu keyakinan sederhana: setiap usaha kecil
di Indonesia berhak hadir secara online dengan cara yang profesional, bukan
sekadar nomor WhatsApp yang beredar dari mulut ke mulut.

Bisnis ini saya kelola sendiri, sambil terus belajar setiap harinya. Dan
justru di situ letak kekuatannya: setiap klien bisa berbicara langsung dengan
orang yang benar-benar mengerjakan websitenya — tidak ada perantara, tidak ada
miskomunikasi.

OnlineUMKM.id lahir dari frustrasi nyata. Banyak warung makan yang luar biasa
tapi sepi karena tidak terlihat di Google. Banyak biro jasa kompeten tapi
kehilangan calon klien karena tak punya website resmi. Masalahnya bukan
kualitas — masalahnya visibilitas digital yang belum tersentuh.

Saat ini kami masih membangun portofolio dan membuka slot gratis untuk UMKM
terpilih sebagai klien perdana — pertukaran yang adil. Kami butuh rekam jejak
nyata, Anda butuh website yang bekerja. Satu hal yang tidak berubah: tidak ada
harga tersembunyi, tidak ada janji kosong.

Sebagai jasa website UMKM yang berfokus pada usaha kecil lokal, kami percaya
kehadiran online bukan lagi kemewahan — itu kebutuhan dasar yang setiap usaha
berhak miliki. OnlineUMKM.id adalah jasa website UMKM yang hadir membantu
usaha kamu tampil di Google, tanpa istilah teknis yang membingungkan. Lihat
layanan kami atau baca tips SEO gratis di blog kami.
```

**Catatan paste ke Elementor:**
- Paste per paragraf ke widget Text Editor
- Kalimat terakhir: blok "layanan kami" → link ke `/` dan blok "tips SEO gratis di blog kami" → link ke `/blog/`
- Jangan paste dalam format Markdown — Elementor tidak membaca `[teks](url)`

**Penempatan keyword "jasa website UMKM":**
1. Paragraf 1 → menyelesaikan cek "frasa kunci di awal" Yoast
2. Paragraf 5 (pertama) → kepadatan konten
3. Paragraf 5 (penutup) → CTA kuat

---

### Versi Panjang (8 paragraf — ±380 kata) ← arsip saja

```
Satu Keyakinan Sederhana

Nama saya Ronald Huson. Saya membangun OnlineUMKM.id — sebuah jasa website
UMKM berbasis di Medan — dari satu keyakinan sederhana: setiap usaha kecil di
Indonesia berhak hadir secara online dengan cara yang profesional, bukan
sekadar nomor WhatsApp yang beredar dari mulut ke mulut.

Ini bukan perusahaan besar, bukan startup dengan puluhan karyawan. Bisnis ini
saya kelola sendiri, sambil terus belajar setiap harinya.

Dan justru di situ letak kekuatannya. Setiap klien bisa berbicara langsung
dengan orang yang benar-benar mengerjakan websitenya — tidak ada perantara,
tidak ada miskomunikasi. Prosesnya terasa mudah, dekat, dan manusiawi.

OnlineUMKM.id lahir dari frustrasi nyata yang saya saksikan sendiri. Banyak
warung makan dengan masakan yang luar biasa, tapi sepi pembeli karena tidak
terlihat di Google. Banyak biro jasa yang kompeten, tapi kehilangan calon
klien karena tidak punya website resmi. Masalahnya bukan kualitas usaha mereka
— masalahnya adalah visibilitas digital yang belum tersentuh.

Saat ini kami masih membangun portofolio. Karena itu, kami membuka beberapa
slot gratis untuk UMKM terpilih sebagai klien perdana — bukan charity, tapi
pertukaran yang adil. Kami butuh rekam jejak nyata. Anda butuh website yang
benar-benar bekerja.

Satu nilai yang tidak pernah kami kompromikan: transparansi. Tidak ada harga
tersembunyi. Tidak ada janji yang tidak bisa kami buktikan. Kalau ada yang
ingin Anda tanyakan, nomor WhatsApp saya ada di halaman ini — dan saya yang
akan menjawabnya langsung.

Sebagai jasa website UMKM yang berfokus pada usaha kecil lokal, kami percaya
satu hal sederhana: kehadiran online bukan lagi kemewahan — itu kebutuhan
dasar yang setiap usaha berhak miliki.

OnlineUMKM.id adalah jasa website UMKM yang hadir untuk membantu usaha kamu
tampil profesional di Google, tanpa istilah teknis yang membingungkan. Lihat
layanan kami atau baca tips SEO gratis di blog kami.
```

---

## Kode Fix Script — Versi Final (Bersih)

Script ini menggantikan **blok fix script** di WordPress homepage (bukan blok HTML utama).

```html
<script>
document.addEventListener('DOMContentLoaded', function() {

  var wa = {
    k:   "https://wa.me/6287791808667?text=Halo%20Ronald%2C%20saya%20ingin%20konsultasi%20gratis%20untuk%20website%20UMKM%20saya",
    w:   "https://wa.me/6287791808667?text=Halo%20Ronald%2C%20saya%20tertarik%20jasa%20pembuatan%20website%20WordPress",
    s:   "https://wa.me/6287791808667?text=Halo%20Ronald%2C%20saya%20tertarik%20jasa%20SEO%20lokal",
    t:   "https://wa.me/6287791808667?text=Halo%20Ronald%2C%20saya%20tertarik%20toko%20online%20WooCommerce",
    c:   "https://wa.me/6287791808667?text=Halo%20Ronald%2C%20saya%20tertarik%20company%20profile",
    cta: "https://wa.me/6287791808667?text=Halo%20Ronald%2C%20saya%20tertarik%20program%20website%20gratis%20untuk%20UMKM%20saya.%20Boleh%20ceritakan%20lebih%20lanjut%3F",
    f:   "https://wa.me/6287791808667"
  };

  function goWA(url) { window.open(url, '_blank'); }
  function goTo(id) {
    var el = document.getElementById(id);
    if (el) el.scrollIntoView({ behavior: 'smooth', block: 'start' });
  }

  /* NAV LINKS */
  var navItems = document.querySelectorAll('.oumkm-page .nav-links li');
  var navMap   = ['layanan', null, 'proses', 'blog', 'faq'];
  navItems.forEach(function(li, i) {
    var a = li.querySelector('a');
    if (!a) return;
    if (a.classList.contains('nav-cta')) {
      a.addEventListener('click', function(e){ e.preventDefault(); goWA(wa.k); });
    } else if (i === 1) {
      a.addEventListener('click', function(e){ e.preventDefault(); window.location.href='/tentang/'; });
    } else if (navMap[i]) {
      (function(t){ a.addEventListener('click', function(e){ e.preventDefault(); goTo(t); }); })(navMap[i]);
    }
  });

  /* HERO BUTTONS */
  var btnWA = document.querySelector('.oumkm-page .btn-wa');
  if (btnWA) btnWA.addEventListener('click', function(){ goWA(wa.k); });
  var btnOutline = document.querySelector('.oumkm-page .btn-outline');
  if (btnOutline) btnOutline.addEventListener('click', function(){ goTo('layanan'); });

  /* LAYANAN CTAs */
  var layCtas = document.querySelectorAll('.oumkm-page .lay-cta');
  var layWA   = [wa.w, wa.s, wa.t, wa.c];
  layCtas.forEach(function(btn, i){
    btn.addEventListener('click', function(){ goWA(layWA[i] || wa.k); });
  });

  /* CTA SECTION */
  var ctaWA = document.querySelector('.oumkm-page .btn-cta-wa');
  if (ctaWA) ctaWA.addEventListener('click', function(){ goWA(wa.cta); });
  var ctaGhost = document.querySelector('.oumkm-page .btn-cta-ghost');
  if (ctaGhost) ctaGhost.addEventListener('click', function(){ goTo('faq'); });

  /* FAQ ACCORDION */
  document.querySelectorAll('.oumkm-page .faq-q').forEach(function(q){
    q.addEventListener('click', function(){
      var ans    = q.nextElementSibling;
      var isOpen = q.classList.contains('open');
      document.querySelectorAll('.oumkm-page .faq-q.open').forEach(function(oq){
        oq.classList.remove('open');
        oq.nextElementSibling.classList.remove('open');
      });
      if (!isOpen){ q.classList.add('open'); ans.classList.add('open'); }
    });
  });

  /* FOOTER LINKS */
  var footerMap = {
    'Pembuatan Website':       function(){ goTo('layanan');                  },
    'Jasa SEO Lokal':          function(){ goTo('layanan');                  },
    'Toko Online WooCommerce': function(){ goTo('layanan');                  },
    'Company Profile':         function(){ goTo('layanan');                  },
    'Tentang Kami':            function(){ window.location.href='/tentang/'; },
    'Cara Kerja':              function(){ goTo('proses');                   },
    'FAQ':                     function(){ goTo('faq');                      },
    'Hubungi Kami':            function(){ goWA(wa.f);                       }
  };
  document.querySelectorAll('.oumkm-page .footer-col ul a').forEach(function(a){
    var txt = a.textContent.trim();
    if (footerMap[txt]){
      a.addEventListener('click', function(e){ e.preventDefault(); footerMap[txt](); });
    }
  });

  /* ============================================
     AUTO-UPDATE BLOG SECTION
     Ambil 3 artikel terbaru dari WordPress REST API
     ============================================ */
  function decodeHtml(html) {
    var txt = document.createElement('textarea');
    txt.innerHTML = html;
    return txt.value;
  }

  function stripHtml(html) {
    var tmp = document.createElement('div');
    tmp.innerHTML = html;
    var text = tmp.textContent || tmp.innerText || '';
    return text.replace(/\[&hellip;\]/g, '').replace(/\[…\]/g, '').trim();
  }

  function pickEmoji(title) {
    var t = title.toLowerCase();
    if (t.indexOf('warung') > -1 || t.indexOf('makan') > -1 || t.indexOf('kuliner') > -1) return '🍜';
    if (t.indexOf('google') > -1 || t.indexOf('maps') > -1 || t.indexOf('business profile') > -1) return '🗺️';
    if (t.indexOf('whatsapp') > -1) return '💬';
    if (t.indexOf('instagram') > -1 || t.indexOf('tiktok') > -1 || t.indexOf('sosial') > -1) return '📱';
    if (t.indexOf('foto') > -1 || t.indexOf('konten') > -1) return '📸';
    if (t.indexOf('iklan') > -1 || t.indexOf('promosi') > -1) return '📣';
    if (t.indexOf('seo') > -1 || t.indexOf('tips') > -1) return '💡';
    if (t.indexOf('website') > -1 || t.indexOf('toko online') > -1) return '🌐';
    return '📝';
  }

  function loadLatestPosts() {
    var container = document.getElementById('blog-grid-dynamic');
    if (!container) return;

    fetch('/wp-json/wp/v2/posts?per_page=3&_embed=true', { credentials: 'same-origin' })
      .then(function(res) {
        if (!res.ok) throw new Error('API error: ' + res.status);
        return res.json();
      })
      .then(function(posts) {
        if (!Array.isArray(posts) || posts.length === 0) return;

        var bgClasses = ['t1', 't2', 't3'];

        var html = posts.map(function(post, i) {
          var title   = decodeHtml(post.title.rendered);
          var excerpt = stripHtml(post.excerpt.rendered);
          if (excerpt.length > 180) excerpt = excerpt.substring(0, 180).trim() + '...';
          var link    = post.link;
          var bgClass = bgClasses[i % 3];

          var catName = 'Artikel';
          if (post._embedded && post._embedded['wp:term'] && post._embedded['wp:term'][0] && post._embedded['wp:term'][0][0]) {
            catName = decodeHtml(post._embedded['wp:term'][0][0].name);
          }

          var thumbHtml = '';
          var fm = post._embedded && post._embedded['wp:featuredmedia'] && post._embedded['wp:featuredmedia'][0];
          if (fm && fm.source_url && !fm.code) {
            thumbHtml = '<div class="blog-thumb ' + bgClass + '" style="background-image:url(' + fm.source_url + ');background-size:cover;background-position:center;"></div>';
          } else {
            thumbHtml = '<div class="blog-thumb ' + bgClass + '">' + pickEmoji(title) + '</div>';
          }

          var fullText = '';
          if (post.content && post.content.rendered) {
            fullText = stripHtml(post.content.rendered);
          }
          var wordCount = fullText ? fullText.split(/\s+/).filter(Boolean).length : 0;
          var readMin = wordCount > 0 ? Math.max(1, Math.round(wordCount / 200)) : 3;

          return '<div class="blog-card">' +
              thumbHtml +
              '<div class="blog-body">' +
                '<div class="blog-meta">' +
                  '<span class="blog-cat">' + catName + '</span>' +
                  '<span class="blog-time">⏱ ' + readMin + ' menit baca</span>' +
                '</div>' +
                '<a class="blog-title" href="' + link + '" target="_blank" rel="noopener">' + title + '</a>' +
                '<p class="blog-excerpt">' + excerpt + '</p>' +
                '<a class="blog-read" href="' + link + '" target="_blank" rel="noopener">Baca Artikel →</a>' +
              '</div>' +
            '</div>';
        }).join('');

        container.innerHTML = html;
      })
      .catch(function(err) {
        console.warn('Blog auto-update gagal, pakai fallback:', err);
      });
  }

  loadLatestPosts();

});
</script>
```

---

## Arsitektur Homepage — Pengingat Penting

Homepage terdiri dari **2 blok HTML terpisah** di WordPress Block Editor:

| Blok | Isi | Cara Edit |
|---|---|---|
| Blok HTML Utama | Seluruh halaman — CSS, nav, hero, sections, footer | Edit via Block Editor, hati-hati |
| Blok Fix Script | Script interaktivitas — semua event listener | **Selalu Ctrl+A → Delete → Paste baru** |

### Aturan Wajib Edit Fix Script
Jangan pernah paste kode baru di atas/di tengah kode lama. Cara aman:
1. Klik di dalam blok fix script
2. **Ctrl+A** — select semua
3. **Delete** — hapus semua
4. **Paste** kode baru lengkap dari atas ke bawah
5. Save

Melanggar aturan ini → JavaScript error → semua tombol mati sekaligus (sudah terjadi satu kali di sesi ini).

---

## Blog Section Homepage — Referensi

Blog section di blok HTML utama kini menggunakan `id="blog-grid-dynamic"`:

```html
<div class="blog-grid" id="blog-grid-dynamic">
  <!-- 3 kartu fallback hardcoded ada di sini -->
  <!-- JavaScript di fix script akan mengganti ini dengan artikel terbaru -->
</div>
```

**Cara kerja:**
- Saat halaman dibuka → JavaScript fetch 3 artikel terbaru dari `/wp-json/wp/v2/posts`
- Kartu lama diganti otomatis dengan artikel terbaru
- Jika fetch gagal → 3 kartu fallback tetap tampil
- Elementor editor akan selalu tampilkan kartu lama (normal — Elementor tidak bisa run JavaScript fetch)
- Live website tampil benar ✅

**Publish artikel baru = otomatis muncul di homepage.** Tidak perlu edit kode apapun.

---

## Failed Attempts (Sesi Ini)

| Percobaan | Kenapa Gagal |
|---|---|
| Edit "frasa kunci di awal" via Elementor | Yoast tidak mendeteksi perubahan — kemungkinan element pertama yang dibaca Yoast bukan yang diedit |
| Edit "frasa kunci dalam subjudul" via Elementor | Kemungkinan widget yang diedit bukan Heading widget — perlu widget Heading (bukan Text) untuk dikenali sebagai H2/H3 |
| Paste kode baru di tengah fix script lama | Mengakibatkan duplikasi kode — semua tombol mati |

---

## Pending — Lanjutkan di Sesi Berikutnya

### Prioritas Tinggi
- [ ] **Paste konten bio baru ke Tentang Kami** (Elementor) — gunakan Versi Ringkas di atas, set internal links "layanan kami" → `/` dan "tips SEO" → `/blog/`
- [ ] **Upload foto Ronald ke Tentang Kami** — menyelesaikan 2 merah Yoast (Gambar + Alt text). Alt text: `Ronald Huson pendiri jasa website UMKM OnlineUMKM Medan`

### Prioritas Menengah
- [ ] **Homepage Keterbacaan Yoast** — masih merah. Butuh penambahan konten prosa di homepage atau penyesuaian teks
- [ ] **Alt text gambar homepage** — logo dan hero image belum optimal (sudah pending dari sesi sebelumnya)

### Prioritas Rendah
- [ ] **Artikel ke-5** — sesuai jadwal konten 12 minggu (sudah ada 4 artikel)
- [ ] **Internal link "Baca juga" di homepage** — cara aman tanpa merusak FAQ accordion

---

## Status Website Keseluruhan per 31 Mei 2026

| Komponen | Status |
|---|---|
| Homepage live | ✅ |
| Blog auto-update | ✅ Aktif |
| Artikel (4 buah) | ✅ Published |
| Halaman Tentang Kami | ✅ Live — konten bio perlu diperbarui |
| Yoast Homepage SEO | ✅ Hijau |
| Yoast Homepage Keterbacaan | 🔴 Merah |
| Yoast Blog | 🟠 Oranye (normal untuk posts archive) |
| Yoast Tentang Kami | 🟠 Oranye (4 merah, 11 hijau) |
| Klien aktif | ❌ Belum ada |

---

*Handoff: Dynamic Blog Homepage + Yoast Fix — 31 Mei 2026*  
*Sesi berikutnya: mulai dari pending Prioritas Tinggi di atas*
