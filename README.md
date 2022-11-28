# Praktikum 6
# Nama :  Bayu Pratama
# Nim : 31221O351
# Kelas : TI.22.A3

# Tugas 6
<img width="585" alt="Screenshot_36" src="https://user-images.githubusercontent.com/115516635/204197503-e392016b-9a1e-4be6-bd68-701c167d33b0.png">


# Penjelasan tugas 6


# 1.) Penggunaan if c.lower()
# jika c.lower() fungsinya apabila user menginputkan denga huruf besar, maka otomatis akan menjadi huruf kecil sehingga kondisi yang digunakan tercapai. Contoh :
# jika c.lower() == q
# 2.) Penggunaan while True
# sedangkan True berfungsi untuk mendeteksi jika format yang diinputkan bukan berupa type maka akan muncul error
# 3.) Penggunaan lain
# Fungsi else jika tidak error dan type yang dimasukan sesuai maka proses sedangkan True
# 4.) Penggunaan valueError
# Fungsinya apabila diinputkan bukan berupa type maka hasilnya error (valueError)


# Code Program

``` Python 
daftarKontak = {"Nama":"Nomer Telpon"}
kontak       = {'Bayu':'081317611667', 'Faiz' : '0881024181723', 'Dapit' : '0877433331430'}

#print
print(30*"═")
print("    Nama    |  Nomor Telepon  ") #prinr daftarkontak
print(30*"-")
print("   # Bayu    | ", kontak['Bayu']) #print kontak Ayubi
print("   # Faiz   | ", kontak['Faiz']) #print kontak Andi
print("   # Dapit   | ", kontak['Dapit']) #print kontak Andi
print(30*"═")

#Tampilkan kontaknya Ayubi
print("Tampilkan kontaknya Ayubi")
print("    Bayu     | ", kontak['Bayu']) #print kontak Ayubi
print(30*"═")
#Tambah kontak baru dengan nama Albed, nomor 081212273539
print("Tambah kontak baru dengan nama Albed, nomor 081212273539")
kontak['Albed'] = '081212273539'
print("    Albed    | ", kontak['Albed'])
print(30*"═")

#Ubah kontak Andi dengan nomor baru 0876780147825
print("Ubah kontak Faiz dengan nomor baru 0881024181723")
kontak['Faiz'] = '0881024181723'
print("    Faiz    | ", kontak['Faiz'])
print(30*"═")

#Tampilkan semua Nama
print("Tampilkan semua Nama")
print(kontak.keys())
print(30*"═")

#Tampilkan semua Nomor
print("Tampilkan semua Nomor")
print(kontak.values())
print(30*"═")

#Tampilkan daftar Nama dan nomornya
print("Tampilkan daftar Nama dan nomornya")
print(kontak.items())
print(30*"═")

#MengHapus kontak Andi
print("Hapus kontak Dapit")
kontak.pop('Dapit')
print(kontak.items())
print(30*"═")
``` 

# Hasil Input Latihan 6 
<img width="960" alt="Screenshot_35" src="https://user-images.githubusercontent.com/115516635/204196553-88ae9af7-34c9-4646-aefe-73e4b4dc99b6.png">

# Tugas 6
<img width="548" alt="Screenshot_37" src="https://user-images.githubusercontent.com/115516635/204197580-75d10461-961e-487e-8df2-b0a69f42ff9a.png">

``` Python
mahasiswa = {}

def show():
    if mahasiswa.items():
        print("Daftar Nilai")
        print("=================================================================================")
        print("| No |      Nama      |     NIM     |  Tugas  |   UTS   |   UAS   |    Akhir    |")
        print("=================================================================================")
        i = 0
        for a in mahasiswa.items():
            i += 1
            print("| {no:2d} | {0:14s} | {1:11s} | {2:7d} | {3:7d} | {4:7d} |      {5:6.2f} |"
            .format (a[0][: 14],a[1][0],a[1][1],a[1][2],a[1][3],a[1][4], no = i))
        print("=================================================================================")
        
    else:
        print("Daftar Nilai")
        print("=================================================================================")
        print("| No |      Nama      |     NIM     |  Tugas  |   UTS   |   UAS   |    Akhir    |")
        print("=================================================================================")
        print("|                                TIDAK ADA DATA                                 |")
        print("=================================================================================")

def add():
    print("Tambah Data")
    nama = input("Nama\t : ")
    nim = input("NIM\t : ")
    uts = int(input("Nilai UTS\t : "))
    uas = int(input("Nilai UAS\t : "))
    tugas = int(input("Nilai Tugas\t : "))
    akhir = (tugas * 30/100) + (uts * 35/100) + (uas * 35/100)
    mahasiswa[nama] = nim, tugas, uts, uas, akhir

def delete():
    print("Hapus Data")
    nama = input("Masukkan Nama : ")
    
    if nama in mahasiswa.keys():
        del mahasiswa[nama]
    
    else:
        print("Nama tidak ditemukan")

def update():
    print("Ubah Data")
    nama = input("Masukkan Nama : ")
    if nama in mahasiswa.keys():
        nim = input("NIM\t : ")
        uts = int(input("Nilai UTS\t : "))
        uas = int(input("Nilai UAS\t : "))
        tugas = int(input("Nilai Tugas\t : "))
        akhir = (tugas * 30/100) + (uts * 35/100) + (uas * 35/100)
        mahasiswa[nama] = nim, tugas, uts, uas, akhir

    else:
        print("Nama tidak ditemukan ")

def search():
    print("Cari Data")
    a = input("Masukkan Nama : ")
    if a in mahasiswa.keys():
        print("===========================================================================")
        print("|      Nama      |     NIM     |  Tugas  |   UTS   |   UAS   |    Akhir   |")
        print("===========================================================================")
        print("| {0:14s} | {1:11s} | {2:7d} | {3:7d} | {4:7d} |     {5:6.2f} |"
            .format (a , mahasiswa[a][0], mahasiswa[a][1], mahasiswa[a][2], mahasiswa[a][3], mahasiswa[a][4] ))
        print("===========================================================================")

    else:
        print("=================================================================================")
        print("| No |      Nama      |     NIM     |  Tugas  |   UTS   |   UAS   |    Akhir    |")
        print("=================================================================================")
        print("|                          DATA TIDAK DITEMUKAN                                 |")
        print("=================================================================================")

def menu():
    print("\n")
    print("================================")
    print("      Program input nilai       ")
    print("================================\n")

    x = input("[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar]: ")
    print("\n")

    if x == 'L':
        show()
    elif x == 'T':
        add()
    elif x == 'U':
        update()
    elif x == 'H':
        delete()
    elif x == 'C':
        search()
    elif x == 'K':
        print("==========================================================================")
        print('\n')
        print("> You exit the code                        ")
        print("\n")
        print("==========================================================================")

        exit()

    else:
        print("            KODE YANG ANDA MASUKKAN TIDAK VALID !!!!!!!!!!!")

while True:
    menu()
```
# Hasil Input
<img width="960" alt="1" src="https://user-images.githubusercontent.com/115516635/204199085-80499ca1-61ea-46c1-9ca9-b15adeee9327.png">

# Flowchart

![ pppp ](https://user-images.githubusercontent.com/115516730/204177502-8a430533-143f-4748-801d-0c4380e12328.png)



