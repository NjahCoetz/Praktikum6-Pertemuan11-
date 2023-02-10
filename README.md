# Praktikum6-Pertemuan11-
# Praktikum6
## Tugas Pertemuan 11 - Bahasa Pemrograman

```sh
Nama   : Azzahra Anugrah Nuralif
Nim    : 312210728
Matkul : Bahasa Pemrograman
```

### 1. File Latihan.py
Program ini adalah program latihan, Yaitu mengubah kode menjadi fungsi menggunakan *"lambda"*.

* **CODINGAN:**
```python
# Latihan 
# Mengubah kode menjadi fungsi menggunakan lambda
import math
def a(x):
    return x**2
    a = lambda x : x ** 2
print(a(2))

def b(x, y):
    return math.sqrt(x**2 + y**2)
    b = lambda x, y : x ** 2  + y ** 2
print(b(2, 2))

def c(*args):
    return sum(args)/len(args)
    c = lambda *args : sum(args)/len(args)
print(c(5, -6, 7, 8))

def d(s):
    return "".join(set(s))
    d = lambda s: "".join(set(s))
print(d("Azzahra"))
```

* **Hasil output program:**

! [Gambar 1](https://github.com/NjahCoetz/Praktikum6-Pertemuan11-/blob/main/ss6.PNG)


### 2. File Praktikum.py

Program ini adalah program sederhana yang akan menampilkan daftar nilai mahasiswa, Program dibuat dengan mengaplikasikan penggunaan *"fungsi"* 
pada python, dengan ketentuan: 
```md
* Fungsi **tambah()** untuk menambah data
* Fungsi **tampilkan()** untuk menampilkan data
* Fungsi **hapus()** untuk menghapus data berdasarkan nama
* Fungsi **ubah()** untuk mengubah data berdasarkan nama
```

* **CODINGAN**
```python
DataMahasiswa = {}

def judul():
    print("=" * 35)
    print("|  PROGRAM INPUT NILAI MAHASISWA  |")
    print("=" * 35)
    print('| 1. Tambah Data                  |')
    print('| 2. Tampilkan Data               |')
    print('| 3. Hapus Data                   |')
    print('| 4. Ubah Data                    |')
    print('| 5. Exit                         |')
    print("=" * 35)
    
judul()

def tambah():
        nama = str(input("\nMasukan Nama      \t: "))
        nim = int(input("Masukan Nim          \t: "))
        tugas = int(input("Masukan Nilai Tugas\t: "))
        uts = int(input("Masukan Nilai UTS\t: "))
        uas = int(input("Masukan Nilai UAS \t: "))
        akhir = (tugas*0.30 + uts*0.35 + uas*0.35)
        DataMahasiswa[nama] = nim, tugas, uts, uas, akhir,
        print("DATA BERHASIL DI TAMBAHKAN!")

def tampilkan():
        print("=" * 69)
        print("|" + "\t" * 3 + "DAFTAR NILAI MAHASISWA" + "\t" * 3 +
                  "    |")
        print("=" * 69)
        print("| NO |   \tNAMA\t   |\tNIM \t| TUGAS | UTS | UAS | AKHIR |")
        print("=" * 69)
        i = 0  
        for tampil in DataMahasiswa.items():
            i += 1
            print("| {6:2} |\t {0:15}   | {1:9} \t| {2:5} | {3:3} | {4:3} | {5:5} |".format(tampil[0], tampil[1][0], tampil[1][1], tampil[1][2], tampil[1][3],"%.2f" % float(tampil[1][4]), i))
            print("=" * 69)

def hapus(nama):
            del DataMahasiswa[nama]
            print("DATA BERHASIL DI HAPUS!")
 
def ubah(nama):
        if nama in DataMahasiswa.keys():
            nim = int(input("Masukan Nim          \t: "))
            tugas = int(input("Masukan Nilai Tugas\t: "))
            uts = int(input("Masukan Nilai UTS\t: "))
            uas = int(input("Masukan Nilai UAS \t: "))
            akhir = (tugas*0.30 + uts*0.35 + uas*0.35)
            DataMahasiswa[nama] = nim, tugas, uts, uas, akhir
            print("\nDATA BERHASIL DI UBAH!")
        else:
            print("\DATA TIDAK DI TEMUKAN!")

while True:
    data = input("(1)Tambah data, (2)Tampilkan data, (3)Hapus data, (4)Ubah data, (5)Keluar \n# pilih menu: ")
   
    if (data.lower() == '1'):
        tambah()

    elif (data.lower() == '4'):
        nama = str(input("\nMasukan Nama        \t: "))
        ubah(nama)
    elif (data.lower() == '3'):
        nama = str(input("\nMasukan Nama        \t: "))
        if nama in DataMahasiswa:
            hapus(nama)
        else:
            print("DATA TIDAK DI TEMUKAN ".format(nama))
    elif (data.lower() == '2'):
        if DataMahasiswa.items():
            tampilkan()
            print(" ")
        else:
            print("=" * 69)
            print("|" + "\t" * 3 + "DAFTAR NILAI MAHASISWA" + "\t" * 3 +
                  "    |")
            print("=" * 69)
            print("| NO |   \tNAMA\t   |\tNIM \t| TUGAS | UTS | UAS | AKHIR |")
            print("=" * 69)
            print("|    " + "\t" * 3 + "TIDAK ADA DATA!" + "\t" * 4 + "    |")
            print("=" * 69)
    elif (data.lower() == '5'):
        print("\nTHANK YOU :) \n")
        exit()
    else:
        print("PILIHAN MENU TIDAK ADA!")
```
