# Super-Cashier
## Latar Belakang
Kasir sederhana yang dibuat dengan menggunakan bahasa pemrograman Python. Projek ini dibuat berdasarkan kebutuhan pemilik supermarket yang membutuhkan fitur-fitur kasir yang mendukung untuk melaksanakan sistem self-service.

## Requirements / Objectives
Dalam proses pembuatannya, projek ini memiliki beberapa requirements dan objectives. Requirements yang ada diantaranya adalah fitur-fitur kasir seperti menambahkan barang, menghapus barang, mengubah barang, membatalkan pembelian, melakukan check out, hingga menghitung total belanja berdasarkan kondisi tertentu. Objektif dari projek ini adalah customer dapat melihat keseluruhan barang yang dibeli, serta jumlah harga yang perlu dibayar.

## Alur Kode
1. Langkah 1.0, kita akan run main.py yang berfungsi sebagai *Main Class*.
2. Langkah 2.0, kita akan mendapatkan output menu dan kita dapat memberikan input berupa angka dari 1 (satu) sampai dengan 8 (delapan)
3. Langkah 3.0, apabila kita memberi input '1', maka kita akan diminta memasukkan input untuk nama customer dan nomor telepon
4. Langkah 3.1, apabila kita memberi input '2', maka kita akan diminta memasukkan input untuk nama barang, jumlah barang, dan harga barang
5. Langkah 3.2, apabila kita memberi input '3', maka kita akan diminta memasukkan input untuk memilih info item yang ingin dirubah
6. Langkah 3.2.1, apabila kita memberi input '1', maka kita akan diminta memasukkan input untuk nama barang yang ingin diganti dan nama barang baru
7. Langkah 3.2.2, apabila kita memberi input '2', maka kita akan diminta memasukkan input untuk nama barang yang jumlahnya ingin diubah dan jumlah barang baru
8. Langkah 3.2.3, apabila kita memberi input '3', maka kita akan diminta memasukkan input untuk nama barang yang harganya ingin diubah dan harga barang baru
9. Langkah 3.3, apabila kita memberi input '4', maka kita akan diminta memasukkan input untuk nama barang yang ingin dihapus
10. Langkah 3.4, apabila kita memberi input '5', maka kita akan mendapatkan output berupa seluruh item yang telah dimasukkan
11. Langkah 3.5, apabila kita memberi input '6', maka kita akan mendapatkan output berupa seluruh item yang telah dimasukkan serta harga total belanja
12. Langkah 3.6, apabila kita memberi input '7', maka kita akan menghapus seluruh item yang telah dimasukkan sebelumnya
13. Langkah 3.7, apabila kita memberi input '8', maka kita akan menghentikan program
14. Langkah 3.8, apabila kita memberi input diluar dari angka 1 (satu) sampai dengan (8), maka akan keluar output "Pilihan salah"
15. Langkah 4.0, program selesai

## Penjelasan Kode
Script main.py berfungsi sebagai *Main Class* yang harus di run pertama kali untuk memunculkan program yang telah dibuat. Didalamnya terdapat function main() sebagai fungsi utama dan menu() untuk menampilkan menu yang dapat user pilih, dan if function untuk memanggil function lainnya.

```
def main():
    '''Fungsi utama untuk menjalankan program
    '''
    while(True):
        menu()
        try:
            '''membuat exception handling apabila terjadi kesalahan 
            atau error dalam program
            '''
            menu_inp = int(input("Masukan pilihan anda: ") )
            if(menu_inp == 1):
                '''branching ini akan dijalankan apabila user menginput '1' 
                '''
                nama_customer = (input("Masukan nama customer: "))
                no_telp = (input("Masukan nomor telepon: "))
                trnsct_123 = module.transaction(nama_customer, no_telp) # membuat ID transaksi customer 
                print("Data customer berhasil diinputkan")

            elif menu_inp == 2:
                '''branching ini akan dijalankan apabila user menginput '2' 
                '''
                nama_item = input("Masukan nama barang: ")
                jumlah_item = str((input("Masukan jumlah barang: ")))
                harga_item = str((input("Masukkan harga barang: ")))
                module.add_item(nama_item, jumlah_item, harga_item)
                print("Data barang berhasil diinputkan")

            elif menu_inp == 3:
                '''branching ini akan dijalankan apabila user menginput '3' 
                '''
                print("Pilihan edit: ")
                print("1. Nama item")
                print("2. Jumlah barang")
                print("3. Harga barang")
                try:
                    update_inp = int(input("Masukan jenis nilai yang ingin diedit: "))
                    if update_inp == 1:
                        '''nested branching ini akan dijalankan apabila user menginput '1' 
                        '''
                        nama_item = input("Masukan nama barang: ")
                        nama_item_baru =  input("Masukan nama barang baru: ")
                        module.update_item_name(nama_item, nama_item_baru)
                        print("Nama barang berhasil diupdate")
                    elif update_inp == 2:
                        '''nested branching ini akan dijalankan apabila user menginput '2' 
                        '''
                        nama_item = input("Masukan nama barang: ")
                        jumlah_item = (input("Masukkan jumlah item: "))
                        module.update_item_qty(nama_item, jumlah_item)
                        print("Nama barang berhasil diupdate")
                    elif update_inp == 3:
                        '''nested branching ini akan dijalankan apabila user menginput '3' 
                        '''
                        nama_item = input("Masukan nama barang: ")
                        harga_item = (input("Masukkan harga item: "))
                        module.update_item_price(nama_item, harga_item)
                        print("Nilai barang berhasil diupdate")
                    else: 
                        '''nested branching ini akan dijalankan apabila user tidak menginput sesuai yang diminta 
                        '''
                        print("Pilihan salah")

                except ValueError:
                    '''exception error ini akan muncul apabila terdapat value error
                    '''
                    print("Terdapat kesalahan input value")

                except Exception:
                    '''exception error ini akan muncul apabila terdapat error yang belum di spesifikan
                    '''
                    print("Terdapat kesalahan")
                
            elif menu_inp == 4:
                '''branching ini akan dijalankan apabila user menginput '4' 
                '''
                nama_item = input("Masukan nama barang: ")
                print("Berhasil menghapus data barang")
                module.delete_item(nama_item)

            elif menu_inp == 5:
                '''branching ini akan dijalankan apabila user menginput '5' 
                '''
                print("Order anda: ")
                module.check_order()

            elif menu_inp == 6:
                '''branching ini akan dijalankan apabila user menginput '6' 
                '''
                module.check_out()

            elif menu_inp == 7:
                '''branching ini akan dijalankan apabila user menginput '7' 
                '''
                print("Barang telah dihapus semua")
                module.reset_transaction()

            elif menu_inp == 8:
                '''branching ini akan dijalankan apabila user menginput '8' 
                '''
                print("Anda telah keluar!")
                return False
            else:
                '''branching ini akan dijalankan apabila user tidak menginput sesuai yang diminta 
                '''
                print("Pilihan salah")
                
        except ValueError:
            print("Terdapat kesalahan input value")

        except Exception:
            print("Terdapat kesalahan")
```
```
def menu():
    '''Fungsi untuk menampilkan pilihan-pilihan yang dapat user pilih'''
    print("Menu: ")
    print("1. Membuat ID Customer") #transaction
    print("2. Menambahkan barang") #add item
    print("3. Update info item") #update item name
    print("4. Menghapus item") #delete item
    print("5. Mengecek order") #check order
    print("6. Check out") #check out
    print("7. Batal belanja") #reset transaction
    print("8. Keluar")
```
```
if __name__ == "__main__":
    '''Digunakan untuk memanggil function main()
    '''
    main()
```

Script module.py digunakan untuk menyimpan function-function yang nantinya akan dipanggil apabila user menginputkan nilai yang sesuai dengan masing-masing kondisi function.

```
nama_customer = None
no_telp = None
list_customer_barang = []
```

```
def transaction(nama_customerr, no_telpp):
    '''Fungsi untuk menerima parameter nama_customerr dan no_telp
       serta mengecek apakah tipe data yang diterima telah sesuai dengan yang diinginkan
    '''
    if type(nama_customerr) != str:
        return False
    if type(no_telpp) != float:
        return False
    nama_customer = nama_customerr
    no_telp = no_telpp
    return True
```
```
def add_item(nama_item, jumlah_item, harga_per_item):
    '''Fungsi untuk menerima parameter nama_item, jumlah_item, dan harga_per_item
       nilai yang diterima akan disimpan kedalam list list_customer_barang
    '''
    print("item yang dibeli adalah: " , nama_item  , "      ", str(jumlah_item) , "      ", str(harga_per_item))
    list_customer_barang.append([nama_item, jumlah_item, harga_per_item])
```
```
def update_item_name(nama_item, nama_item_baru):
    '''Fungsi untuk menerima parameter nama_item, dan nama_item_baru
       Fungsi ini digunakan untuk mengganti nama item yang telah dimasukkan sebelumnya
       dengan nama yang baru
    '''
    for nama in list_customer_barang:
        if nama[0] == nama_item:
            nama[0] = nama_item_baru
    return True
```
```
def update_item_qty(nama_item, jumlah_item):
    '''Fungsi untuk menerima parameter nama_item, dan jumlah_item
       Fungsi ini digunakan untuk mengganti jumlah item yang telah dimasukkan sebelumnya
       dengan jumlah item yang baru
    '''
    for nama in list_customer_barang:
        if nama[0] == nama_item:
            nama[1] = jumlah_item
    return True
```
```
def update_item_price(nama_item, harga_item):
    '''Fungsi untuk menerima parameter nama_item, dan harga_item
       Fungsi ini digunakan untuk mengganti harga item yang telah dimasukkan sebelumnya
       dengan harga item yang baru
    '''
    for nama in list_customer_barang:
        if nama[0] == nama_item:
            nama[2] = harga_item
    return True
```
```
def delete_item(nama_item):
    '''Fungsi untuk menerima parameter nama_item
       Fungsi ini digunakan untuk menghapus barang yang telah dimasukkan sebelumnya
       menggunakan nama item yang ingin dihapus
    '''
    for index, nama in enumerate(list_customer_barang):
        if nama[0] == nama_item:
            break
    list_customer_barang.pop(index)
    print(list_customer_barang)
    return True
```
```
def check_order():
    '''Fungsi ini digunakan untuk mencetak seluruh item yang dimasukkan
       serta mengecek apakah ada kesalahan input data
    '''
    for nama in list_customer_barang:
        if nama[0] == "" or nama[1] == "" or nama[2] == "":
            print("Terdapat kesalahan input data")
            break
    else:
        print("Pemesanan sudah benar")
        print(list_customer_barang)
    return True
```
```
nomor_id = 0 # diletakkan di luar fungsi agar tidak merubah nilai variabel menjadi 0 setiap kali dijalankan
def number():
    '''Fungsi ini digunakan untuk membuat increment pada nomor_id'''
    global nomor_id
    nomor_id += 1
```
```
def check_out():
    '''Fungsi ini digunakan untuk menghitung total harga, diskon, dan harga setelah diskon
       kepada item-item yang telah dimasukkan sebelumnya
    '''
    number()
    total_harga = 0
    jumlah_akhir = 0
    diskon = 0
    harga_diskon = 0

    for nama in list_customer_barang:
        total_harga = int(nama[1]) * int(nama[2])
        jumlah_akhir = total_harga + jumlah_akhir

    if jumlah_akhir > 200000 and jumlah_akhir <= 300000:
        diskon = jumlah_akhir*0.05
        harga_diskon = jumlah_akhir - diskon

    elif jumlah_akhir > 300000 and jumlah_akhir <= 500000:
        diskon = jumlah_akhir*0.06
        harga_diskon = jumlah_akhir - diskon

    elif jumlah_akhir > 500000:
        diskon = jumlah_akhir*0.07
        harga_diskon = jumlah_akhir - diskon

    else:
        diskon = 0
        harga_diskon = jumlah_akhir - diskon
    print("Item yang dibeli adalah: ", list_customer_barang)
    print("Total harga belanja: ", harga_diskon)
    return True
```
```
def reset_transaction():
    '''Fungsi untuk menghapus seluruh item yang telah digunakan sebelumnya'''
    list_customer_barang.clear()
    return True
```

## Test Case
1. Menambahkan item baru

![image](https://user-images.githubusercontent.com/118685091/228756228-2a0ac27a-6e17-4601-8074-6e72593e95b2.png)

![image](https://user-images.githubusercontent.com/118685091/228756304-66860a3f-f19d-4ba0-b5f1-947d58f1ab6c.png)

2. Menghapus salah satu item

![image](https://user-images.githubusercontent.com/118685091/228756886-0202381f-5902-44ff-8adb-373edf819fcd.png)

3. Menghapus seluruh item

![image](https://user-images.githubusercontent.com/118685091/228757078-c810ceaa-57f8-4f51-8a02-48d68baf9eda.png)

4. Menambahkan item baru

![image](https://user-images.githubusercontent.com/118685091/228758217-5cfab657-659a-43b3-bcea-a0b2b010aa85.png)

![image](https://user-images.githubusercontent.com/118685091/228758321-fa8c8322-6865-4a67-9138-cd41bf15f458.png)

![image](https://user-images.githubusercontent.com/118685091/228758397-93e6a93c-2011-4549-a0db-13547c79fa70.png)

![image](https://user-images.githubusercontent.com/118685091/228757917-d00538db-dea8-4b6f-8dea-69a8a677d57c.png)

5. Melakukan Check Out

![image](https://user-images.githubusercontent.com/118685091/228759176-40b90848-eb74-4846-a1d3-197503b3e823.png)

## Conclusion/Future Work
Secara singkat, projek yang telah dibuat sudah layak untuk digunakan. Fitur-fitur yang ada sudah teruji performanya yang dibuktikan dengan test case, diantaranya adalah menambahkan item, menghapus item, membatalkan transaksi, dan melakukan check out. Meskipun begitu, program yang telah dibuat dapat ditingkatkan kembali kualitasnya. Misalnya adalah membuat fitur-fitur baru, seperti list item yang tersedia, membuat user interface, tanggal pembelian, dan lain-lain.
