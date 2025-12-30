## Dasar Teori
# <h1 align="center">Laporan Praktikum Modul 2 - Codeblocks IDE & Pengenalan Bahas C++ (Bagian Kedua)</h1>
<p align="center">Erlina Dwi Setyani - 103112430229</p>

## Dasar Teori
Bahasa C++ adalah jenis bahasa pemrograman yang berada di tingkat menengah. Bahasa ini sering digunakan dalam belajar serta mengembangkan perangkat lunak karena mendukung pemrograman yang terstruktur dan berorientasi objek. 
Dalam praktikum ini, mahasiswa akan mempelajari konsep-konsep lanjutan dari C++, yang termasuk penggunaan struktur kontrol seperti percabangan dan perulangan, pembuatan dan pemanggilan fungsi, penggunaan array, serta penerapan tipe data dan operator. 
Memahami konsep-konsep ini sangat penting agar mahasiswa dapat menulis program yang teratur, efisien, dan sesuai dengan kebutuhan untuk memecahkan masalah dalam praktik pemrograman.

## Unguided 

### 1. Penjumlahan, Pengurangan, dan Perkalian Matriks 3x3

```C++
#include <iostream>
using namespace std;

int main() {
    int A[3][3], B[3][3];
    int tambah[3][3], kurang[3][3], kali[3][3];

    cout << "Input Matriks A (3x3)\n";
    for(int i = 0; i < 3; i++){
        for(int j = 0; j < 3; j++){
            cin >> A[i][j];
        }
    }

    cout << "\nInput Matriks B (3x3)\n";
    for(int i = 0; i < 3; i++){
        for(int j = 0; j < 3; j++){
            cin >> B[i][j];
        }
    }

    for(int i = 0; i < 3; i++){
        for(int j = 0; j < 3; j++){
            tambah[i][j] = A[i][j] + B[i][j];
            kurang[i][j] = A[i][j] - B[i][j];
        }
    }

    for(int i = 0; i < 3; i++){
        for(int j = 0; j < 3; j++){
            kali[i][j] = 0;
            for(int k = 0; k < 3; k++){
                kali[i][j] += A[i][k] * B[k][j];
            }
        }
    }

    cout << "\nHasil Penjumlahan:\n";
    for(int i = 0; i < 3; i++){
        for(int j = 0; j < 3; j++){
            cout << tambah[i][j] << " ";
        }
        cout << endl;
    }

    cout << "\nHasil Pengurangan:\n";
    for(int i = 0; i < 3; i++){
        for(int j = 0; j < 3; j++){
            cout << kurang[i][j] << " ";
        }
        cout << endl;
    }

    cout << "\nHasil Perkalian:\n";
    for(int i = 0; i < 3; i++){
        for(int j = 0; j < 3; j++){
            cout << kali[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```
penjelasan singkat guided 1
Program C++ di atas digunakan untuk mengolah dua buah matriks berukuran 3×3, yaitu matriks A dan matriks B. program meminta pengguna untuk memasukkan nilai setiap elemen pada matriks A dan matriks B.
Hasil dari setiap operasi, yaitu penjumlahan, pengurangan, dan perkalian matriks, kemudian ditampilkan ke layar.

##### Output 1
![Screenshot Output Unguided 1_1](https://github.com/erlina1909/.Struktur-Data-Assignment.git)

### 2. Pointer dan Reference

```C++
#include <iostream>
using namespace std;

void tukarPointer(int *a, int *b, int *c) {
    int temp = *a;
    *a = *b;
    *b = *c;
    *c = temp;
}

void tukarReference(int &a, int &b, int &c) {
    int temp = a;
    a = b;
    b = c;
    c = temp;
}

int main() {
    int x, y, z;

    cout << "Masukkan nilai x y z: ";
    cin >> x >> y >> z;

    tukarPointer(&x, &y, &z);
    cout << "\nSetelah ditukar (Pointer): ";
    cout << x << " " << y << " " << z << endl;

    tukarReference(x, y, z);
    cout << "Setelah ditukar (Reference): ";
    cout << x << " " << y << " " << z << endl;

    return 0;
}

```
penjelasan singkat guided 2
Program C++ di atas bertujuan untuk menukar nilai tiga variabel menggunakan dua cara, yaitu pointer dan reference. Program dimulai dengan meminta pengguna memasukkan nilai untuk variabel x, y, dan z.
Setelah masing-masing fungsi dijalankan, hasil pertukaran nilai ditampilkan ke layar untuk menunjukkan perbedaan cara kerja pointer dan reference dalam C++.

##### Output 1
![Screenshot Output Unguided 1_2](https://github.com/erlina1909/.Struktur-Data-Assignment.git)

### 3. Switch Case

```C++
#include <iostream>
using namespace std;

int cariMinimum(int arr[], int n) {
    int min = arr[0];
    for(int i = 1; i < n; i++){
        if(arr[i] < min)
            min = arr[i];
    }
    return min;
}

int cariMaksimum(int arr[], int n) {
    int max = arr[0];
    for(int i = 1; i < n; i++){
        if(arr[i] > max)
            max = arr[i];
    }
    return max;
}

void hitungRataRata(int arr[], int n) {
    float total = 0;
    for(int i = 0; i < n; i++){
        total += arr[i];
    }
    cout << "Nilai rata-rata = " << total / n << endl;
}

int main() {
    int arrA[10] = {11, 8, 5, 7, 12, 26, 3, 54, 33, 55};
    int pilihan;

    do {
        cout << "\n--- Menu Program Array ---\n";
        cout << "1. Tampilkan isi array\n";
        cout << "2. Cari nilai maksimum\n";
        cout << "3. Cari nilai minimum\n";
        cout << "4. Hitung nilai rata-rata\n";
        cout << "5. Keluar\n";
        cout << "Pilih menu: ";
        cin >> pilihan;

        switch(pilihan) {
            case 1:
                for(int i = 0; i < 10; i++){
                    cout << arrA[i] << " ";
                }
                cout << endl;
                break;
            case 2:
                cout << "Nilai maksimum = "
                     << cariMaksimum(arrA, 10) << endl;
                break;
            case 3:
                cout << "Nilai minimum = "
                     << cariMinimum(arrA, 10) << endl;
                break;
            case 4:
                hitungRataRata(arrA, 10);
                break;
            case 5:
                cout << "Program selesai\n";
                break;
            default:
                cout << "Pilihan tidak valid\n";
        }
    } while(pilihan != 5);

    return 0;
}

```
penjelasan singkat guided 3
Program C++ di atas merupakan program berbasis menu yang digunakan untuk mengolah sebuah array berisi 10 bilangan.
engguna dapat memilih menu untuk menampilkan isi array, mencari nilai maksimum atau minimum, menghitung rata-rata, atau keluar dari program. Program akan terus berjalan menggunakan perulangan hingga pengguna memilih menu keluar, kemudian menampilkan hasil sesuai dengan pilihan yang dipilih.

##### Output 1
![Screenshot Output Unguided 1_3](https://github.com/erlina1909/.Struktur-Data-Assignment.git)

## Kesimpulan
Berdasarkan hasil praktikum dan pembahasan pada modul dapat disimpulkan bahwa Melalui praktikum ini,
mahasiswa dapat mengimplementasikan teori yang telah dipelajari ke dalam bentuk program sederhana, sehingga mampu meningkatkan keterampilan logika pemrograman dan pemecahan masalah secara sistematis.

## Referensi
[1] Modul Praktikum Struktur Data. Modul 2: Pengenalan Bahasa C++ (Bagian Kedua). Program Studi Informatika, Semester Ganjil 2025/2026.
[2] Frieyadie, Dalis, S., & Sari, P. C. (2014). Modul Praktikum Pemrograman C++ Menggunakan Borland C++ 5.02. Jakarta: Akademi Manajemen Informatika dan Komputer Bina Sarana Informatika. 
