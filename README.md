# tugas_logika_informatika

## Code input 
```python
def hitung_biaya_pengiriman(berat, jarak, jenis_pengiriman, is_member):
    # Biaya dasar pengiriman
    biaya_dasar = 10000  # Misalnya Rp 10.000 sebagai biaya dasar

    # Konversi berat dan jarak ke satuan yang sesuai
    berat_paket_gram = berat * 1000  # Konversi kg ke gram
    jarak_pengiriman_meter = jarak * 1000  # Konversi km ke meter

    # Inisialisasi total pembayaran dengan biaya dasar
    total_pembayaran = biaya_dasar

    # Tambahan biaya jika berat melebihi 5000 gram (5 kg)
    if berat_paket_gram > 5000:
        total_pembayaran += 5000

    # Tambahan biaya jika jarak melebihi 10 km (10.000 meter)
    if jarak_pengiriman_meter > 10000:
        total_pembayaran += 8000

    # Tambahan biaya untuk pengiriman express
    if jenis_pengiriman.lower() == 'express':
        total_pembayaran += 20000

    # Diskon untuk member (10% dari total)
    if is_member:
        total_pembayaran -= total_pembayaran * 10 / 100  # Diskon 10%

    return int(total_pembayaran)  # Mengembalikan nilai sebagai integer
# =====================================================
# Program Utama (Meminta Input dari Pengguna)
# =====================================================
if __name__ == "__main__":
    print("=== Program Perhitungan Biaya Pengiriman ===")

    # 1. Memasukkan berat paket
    while True:
        try:
            berat_paket = float(input("Masukkan berat paket (kg): "))
            if berat_paket < 0:
                print("Berat paket tidak bisa negatif. Silakan masukkan kembali.")
                continue
            break
        except ValueError:
            print("Input tidak valid! Masukkan angka.")

    # 2. Memasukkan jarak pengiriman
    while True:
        try:
            jarak_pengiriman = float(input("Masukkan jarak pengiriman (km): "))
            if jarak_pengiriman < 0:
                print("Jarak tidak bisa negatif. Silakan masukkan kembali.")
                continue
            break
        except ValueError:
            print("Input tidak valid! Masukkan angka.")

    # 3. Memasukkan jenis pengiriman (biasa/express)
    while True:
        jenis_pengiriman = input("Masukkan jenis pengiriman (biasa/express): ").strip().lower()
        if jenis_pengiriman not in ["biasa", "express"]:
            print("Jenis pengiriman hanya bisa 'biasa' atau 'express'. Silakan masukkan kembali.")
        else:
            break

    # 4. Memasukkan status keanggotaan pelanggan (member atau bukan)
    while True:
        is_member_input = input("Apakah pelanggan member? (ya/tidak): ").strip().lower()
        if is_member_input in ["ya", "tidak"]:
            is_member = is_member_input == "ya"
            break
        else:
            print("Harap masukkan 'ya' atau 'tidak'.")

    # 5. Menghitung biaya pengiriman
    biaya = hitung_biaya_pengiriman(berat_paket, jarak_pengiriman, jenis_pengiriman, is_member)

    # 6. Menampilkan hasil
    print("\n=== Rincian Biaya Pengiriman ===")
    print(f"Berat paket         : {berat_paket} kg")
    print(f"Jarak pengiriman    : {jarak_pengiriman} km")
    print(f"Jenis pengiriman    : {jenis_pengiriman.capitalize()}")
    print(f"Status Member       : {'Ya' if is_member else 'Tidak'}")
    print(f"Total Biaya Pengiriman: Rp {biaya:,.0f}")

    print("="*64)
    print("NAMA : Aldi Rismandayana".center(64))
    print(f'NIM : {312410015}'.center(64))
    print("="*64)
```


## Output 
````markdown
=== Program Perhitungan Biaya Pengiriman ===
Masukkan berat paket (kg): 90
Masukkan jarak pengiriman (km): 100
Masukkan jenis pengiriman (biasa/express): biasa
Apakah pelanggan member? (ya/tidak): ya

=== Rincian Biaya Pengiriman ===
Berat paket         : 90.0 kg
Jarak pengiriman    : 100.0 km
Jenis pengiriman    : Biasa
Status Member       : Ya
Total Biaya Pengiriman: Rp 20,700
================================================================
                    NAMA : Aldi Rismandayana
                        NIM : 312410015
================================================================
=== Program Perhitungan Biaya Pengiriman ===
Masukkan berat paket (kg): 90
Masukkan jarak pengiriman (km): 100
Masukkan jenis pengiriman (biasa/express): biasa
Apakah pelanggan member? (ya/tidak): tidak

=== Rincian Biaya Pengiriman ===
Berat paket         : 90.0 kg
Jarak pengiriman    : 100.0 km
Jenis pengiriman    : Biasa
Status Member       : Tidak
Total Biaya Pengiriman: Rp 23,000
================================================================
                    NAMA : Aldi Rismandayana
                        NIM : 312410015
================================================================
=== Program Perhitungan Biaya Pengiriman ===
Masukkan berat paket (kg): 99
Masukkan jarak pengiriman (km): 100
Masukkan jenis pengiriman (biasa/express): express
Apakah pelanggan member? (ya/tidak): ya

=== Rincian Biaya Pengiriman ===
Berat paket         : 99.0 kg
Jarak pengiriman    : 100.0 km
Jenis pengiriman    : Express
Status Member       : Ya
Total Biaya Pengiriman: Rp 38,700
================================================================
                    NAMA : Aldi Rismandayana
                        NIM : 312410015
================================================================
=== Program Perhitungan Biaya Pengiriman ===
Masukkan berat paket (kg): 99
Masukkan jarak pengiriman (km): 100
Masukkan jenis pengiriman (biasa/express): express
Apakah pelanggan member? (ya/tidak): ya

=== Rincian Biaya Pengiriman ===
Berat paket         : 99.0 kg
Jarak pengiriman    : 100.0 km
Jenis pengiriman    : Express
Status Member       : Ya
Total Biaya Pengiriman: Rp 38,700
================================================================
                    NAMA : Aldi Rismandayana
                        NIM : 312410015
================================================================
````

## Penjelasan 
Kode program ini adalah sebuah aplikasi sederhana untuk menghitung biaya pengiriman paket. Program ini dimulai dengan mendefinisikan sebuah fungsi bernama hitung_biaya_pengiriman. Fungsi ini menerima empat parameter: berat paket, jarak pengiriman, jenis pengiriman (biasa atau express), dan status keanggotaan pelanggan (member atau bukan). Di dalam fungsi, biaya dasar pengiriman ditetapkan sebesar Rp10.000. Berat dan jarak dikonversi ke gram dan meter untuk perhitungan yang lebih detail. Kemudian, program menambahkan biaya tambahan jika berat paket melebihi 5 kg atau jarak pengiriman melebihi 10 km. Jika jenis pengiriman adalah "express", ada tambahan biaya lagi. Terakhir, jika pelanggan adalah member, mereka mendapatkan diskon 10% dari total biaya. Fungsi ini mengembalikan total biaya pengiriman dalam bentuk integer. Bagian utama dari program ini meminta pengguna untuk memasukkan berat paket, jarak pengiriman, jenis pengiriman, dan status keanggotaan. Program menggunakan loop while dan blok try-except untuk memastikan input yang dimasukkan valid (misalnya, berat dan jarak tidak negatif, jenis pengiriman dan status keanggotaan sesuai pilihan). Setelah semua input diperoleh, program memanggil fungsi hitung_biaya_pengiriman untuk menghitung total biaya. Hasil perhitungan kemudian ditampilkan kepada pengguna, bersama dengan rincian input yang telah dimasukkan. Terakhir, program menampilkan informasi pembuat program, yaitu nama dan NIM. Secara keseluruhan, program ini dirancang untuk menjadi mudah digunakan dan memberikan perhitungan biaya pengiriman yang akurat berdasarkan parameter yang diberikan.

## Cara kerja Program 
Program ini dirancang untuk menghitung biaya pengiriman paket. Pertama-tama, program meminta pengguna untuk memasukkan informasi terkait pengiriman, seperti berat paket, jarak pengiriman, jenis pengiriman (biasa atau express), dan status keanggotaan pelanggan. Program kemudian melakukan validasi input untuk memastikan data yang dimasukkan sesuai dengan format yang diharapkan. Setelah semua input valid, program memanggil fungsi khusus yang menghitung biaya pengiriman berdasarkan aturan yang telah ditentukan. Fungsi ini memperhitungkan biaya dasar, biaya tambahan berdasarkan berat dan jarak, biaya tambahan untuk pengiriman express, dan diskon untuk member. Hasil perhitungan biaya kemudian ditampilkan kepada pengguna bersama dengan rincian informasi pengiriman yang dimasukkan. Terakhir, program menampilkan informasi pembuat program sebagai penanda. Secara keseluruhan, program ini memberikan solusi praktis untuk menghitung biaya pengiriman dengan mempertimbangkan berbagai faktor yang relevan.
