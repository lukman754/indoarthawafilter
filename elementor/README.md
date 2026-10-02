# Elementor Export

HTML di folder `sections/` adalah blok siap tempel untuk Elementor. Setiap file berisi markup dan CSS scoped dengan prefix `af-`, jadi tidak membutuhkan stylesheet dari folder `css/` dan kecil kemungkinan bentrok dengan theme.

## Cara pakai

1. Buat page di Elementor. Untuk tampilan selebar desain ini, gunakan layout full width, atur background halaman ke `#f1f3f2`, dan hilangkan padding tambahan pada parent container. Masing-masing blok sudah mengatur lebar dan padding internalnya.
2. Tambahkan satu widget **HTML** untuk setiap section yang dibutuhkan.
3. Buka file terkait di `sections/`, salin seluruh isinya termasuk tag `<style>`, lalu tempel ke widget HTML.
4. Untuk halaman lengkap, urutannya: `navigation`, `hero`, `intro`, `products`, `system`, `process`, `quote`, `footer`. Header/footer boleh dilewati jika sudah disediakan theme atau Elementor Theme Builder.
5. Preview di desktop dan mobile. Link antarsection memakai ID dengan prefix `af-`, jadi blok yang menjadi target harus ikut dipasang pada halaman yang sama.

## Yang perlu disesuaikan

- Di `hero.html`, ganti `https://your-domain.vercel.app` dengan domain Vercel yang sebenarnya. File `model-3d.html` harus ikut ter-deploy di root domain tersebut. Jika tidak ingin menampilkan model, hapus elemen iframe dari snippet.
- Form di `quote.html` hanya tampilan dan belum mengirim data. Untuk menerima request, ganti form HTML dengan Elementor Form atau hubungkan ke endpoint/WhatsApp yang benar.
- Font Manrope dan foto produk dimuat dari layanan eksternal (Google Fonts dan Unsplash). Untuk kontrol jangka panjang, unggah aset ke WordPress sendiri dan ubah URL-nya.
- Navigasi mobile saat ini menyembunyikan link, mengikuti versi situs statis.
- Setiap snippet mengimpor Manrope sendiri. Browser biasanya memakai cache untuk permintaan font yang sama.

## Vercel dan sumber utama

Situs utama tetap di root repo (`index.html` dan `model-3d.html`) dengan CSS di `css/`. Deploy repo di Vercel sebagai static site: framework preset **Other**, build command kosong, output directory `.`. Tidak perlu dependency atau build step.

Perbarui `index.html` dan CSS sebagai versi utama. Jika ada perubahan desain yang ingin dibawa ke Elementor, perbarui snippet terkait di folder ini juga. Snippet Elementor adalah ekspor siap tempel, bukan file yang otomatis dibuat dari halaman utama.
