# pratikum6
# Data Diri
Nama : Rafli Dhiya fadhaly

Nim : 312410251

Kelas : TI 24 A2
# Pratkikum 6
Program pertama yang akan dibuat adalah Program untuk menampilkan angka pertama dan kedua dan masukan operator dan mendapat hasil dari masukan

Berikut Flowchart
![Draw ioi](https://github.com/user-attachments/assets/75a0e3a4-951c-4ceb-99bb-aa30a95244ce)

Program akan meminta kita untuk memasukkan tambah data siswa, menampilkan data siswa, menghapus data siswa, mengubah data siswa, keluar:

![Screenshot (107)](https://github.com/user-attachments/assets/ec65ba83-46d2-4c9e-bc4d-1b942bd9ff7f)
# Penjelasan Kode
```python
def tambah(data_mahasiswa):
  nama = input("Masukkan nama mahasiswa: ")
  nilai = float(input("Masukkan nilai mahasiswa: "))
  data_mahasiswa.append({"nama": nama, "nilai": nilai})
  print("Data mahasiswa berhasil ditambahkan.")

def tampilkan(data_mahasiswa):
  if not data_mahasiswa:
    print("Data mahasiswa masih kosong.")
  else:
    print("Daftar Nilai Mahasiswa:")
    print("--------------------------")
    for mahasiswa in data_mahasiswa:
      print(f"Nama: {mahasiswa['nama']} , Nilai: {mahasiswa['nilai']}")
      print("--------------------------")

def hapus(data_mahasiswa, nama):
  for i, mahasiswa in enumerate(data_mahasiswa):
    if mahasiswa['nama'] == nama:
      del data_mahasiswa[i]
      print(f"Data mahasiswa dengan nama {nama} berhasil dihapus.")
      return
  print(f"Data mahasiswa dengan nama {nama} tidak ditemukan.")

def ubah(data_mahasiswa, nama):
  for mahasiswa in data_mahasiswa:
    if mahasiswa['nama'] == nama:
      nilai_baru = float(input("Masukkan nilai baru: "))
      mahasiswa['nilai'] = nilai_baru
      print(f"Data mahasiswa dengan nama {nama} berhasil diubah.")
      return
  print(f"Data mahasiswa dengan nama {nama} tidak ditemukan.")

# Inisialisasi data mahasiswa
data_mahasiswa = []

# Menu program
while True:
  print("\nMenu:")
  print("1. Tambah data mahasiswa")
  print("2. Tampilkan data mahasiswa")
  print("3. Hapus data mahasiswa")
  print("4. Ubah data mahasiswa")
  print("5. Keluar")
  pilihan = input("Pilih menu (1/2/3/4/5): ")

  if pilihan == '1':
    tambah(data_mahasiswa)
  elif pilihan == '2':
    tampilkan(data_mahasiswa)
  elif pilihan == '3':
    nama = input("Masukkan nama mahasiswa yang ingin dihapus: ")
    hapus(data_mahasiswa, nama)
  elif pilihan == '4':
    nama = input("Masukkan nama mahasiswa yang ingin diubah: ")
    ubah(data_mahasiswa, nama)
  elif pilihan == '5':
    break
  else:
    print("Pilihan tidak valid.")
```
# Penjelasan
•  tambah(data_mahasiswa)
Fungsi ini menambahkan data mahasiswa ke dalam daftar:
•	Mengambil input dari pengguna untuk nama dan nilai mahasiswa.
•	Menyimpan data tersebut dalam format dictionary ({"nama": nama, "nilai": nilai}).
•	Menambahkan dictionary ini ke dalam list data_mahasiswa.
•  tampilkan(data_mahasiswa)
Fungsi ini menampilkan seluruh data mahasiswa:
•	Memeriksa apakah daftar mahasiswa kosong.
•	Jika tidak kosong, mencetak daftar mahasiswa beserta nilai mereka dalam format yang rapi.
•  hapus(data_mahasiswa, nama)
Fungsi ini menghapus data mahasiswa berdasarkan nama:
•	Mencari nama mahasiswa dalam daftar.
•	Jika ditemukan, menghapus data tersebut dan memberi pesan konfirmasi.
•	Jika tidak ditemukan, menampilkan pesan kesalahan.
•  ubah(data_mahasiswa, nama)
Fungsi ini mengubah nilai mahasiswa berdasarkan nama:
•	Mencari mahasiswa dengan nama yang sesuai.
•	Jika ditemukan, meminta input nilai baru dan memperbarui data.
•	Jika tidak ditemukan, menampilkan pesan kesalahan.
•  Menampilkan Menu:
Menampilkan opsi seperti menambah, menampilkan, menghapus, atau mengubah data mahasiswa.
•  Membaca Input Pengguna:
Pengguna memilih opsi dengan memasukkan angka 1 hingga 5:
•	1: Menambah data mahasiswa.
•	2: Menampilkan semua data mahasiswa.
•	3: Menghapus data mahasiswa berdasarkan nama.
•	4: Mengubah nilai mahasiswa.
•	5: Keluar dari program.
•  Validasi Input:
Jika input tidak valid (bukan angka 1-5), program akan menampilkan pesan kesalahan.
