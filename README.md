# ROV-LPKTA-2017
ROV LPKTA FT UGM adalah Robot Bawah Air berbasis ROV yang berfungsi mencari, memetakan dan meledakkan ranjau laut.

## Panduan Kontribusi
Clone repository ini. Lalu download dan install library berikut pada Arduino IDE:

 - [LiquidCrystal_I2C](https://github.com/marcoschwartz/LiquidCrystal_I2C)
 - [Due Timer](https://github.com/ivanseidel/DueTimer)
 - [PID Library](https://github.com/br3ttb/Arduino-PID-Library/)
 - _Library lain?_[library lain menyusul]

#### Alur Kerja
Alur kerja repository ini mengikuti [GitHub Flow](https://guides.github.com/introduction/flow/):

 1. Buat _**branch**_ baru untuk setiap fitur baru, pengembangan atau perbaikan. Contohnya `kontrol-gerak`, `atur-kecepatan` atau `kontrol-gripper`.
 2. Mulai buat perubahan, lalu _**commit**_ secara berkala. Tambahkan _commit message_ yang jelas dan rapi.
 3. Buat sebuah _**pull request**_. _Pull request_ memulai sebuah sesi diskusi yang dapat digunakan untuk menyampaikan ide, meminta bantuan, atau melakukan review kode bersama. Pastikan sebuah _pull request_ dibuat setelah fitur baru selesai agar dapat direview oleh programmer lain.
 4. Diskusikan dan review kode yang telah dibuat. Langkah ini memastikan setiap kode terhindar dari bug dan _style_ kodenya konsisten.
 5. Tes pada hardware untuk memastikan semua bekerja dengan baik.
 6. Jika semuanya lancar, _**merge**_ perubahan ke _branch_ master.

## Gaya Pemrograman
Program ROV LPKTA dibuat untuk mikrokontroler Arduino Due. Maka gaya pemrograman diadopsi dari [Arduino API Style Guide](https://www.arduino.cc/en/Reference/APIStyleGuide) dengan beberapa penyesuaian.

#### Penamaan File
Nama file dimulai dengan huruf kapital pada setiap kata. Jika terdapat lebih dari satu kata, spasi dihilangkan. Contoh:

- `Kamera.h`
- `InverseKinematics.c`

Agar bisa di-_compile_ dengan baik oleh Arduino IDE, seluruh source code harus disimpan langsung pada direktori `ROV-LPKTA`, dan tidak disimpan pada direktori lain di dalam `ROV-LPKTA`.

#### Penamaan Fungsi, Variabel, Konstanta dan Makro
Nama variabel dibuat underscore case. Contoh:
- `char motor`
- `int koordinat_awal`

Nama fungsi dibuat camel case. Contoh:

- `digitalRead()`

Nama konstanta dan makro dibuat kapital dan dipisahkan oleh `_` jika lebih dari satu kata. Contoh:

- `KONSTANTA`
- `KONSTANTA_LAIN`

Gunakan nama yang singkat padat dan jelas, hindari nama yang ambigu.

#### Indentasi
Indentasi pada Arduino IDE menggunakan 2 spasi, sedangkan kebanyakan standar lain menggunakan 4 spasi. Indentasi 2 spasi lebih sulit dibaca, terutama pada kode yang bersarang. Jadi lebih baik menggunakan **4 spasi**.

Cara mengatur Arduino IDE menjadi 4 spasi:

1. Masuk ke `File > Preferences` atau tekan `Ctrl + ,`.
2. Pada `More preferences can be edited directly in the file` klik pada lokasi filenya.
3. Tutup Arduino IDE, lalu buka `preferences.txt`
4. Ubah `editor.tabs.size=2` menjadi `editor.tabs.size=4`, lalu simpan.

#### Penempatan `{` dan `}`
Agar mudah melihat batasan _scope_ setiap blok program, tempatkan `{` dan `}` pada baris sendiri. Contoh:

```c++
void contoh()
{
	if (1)
	{
		// Kode
	}
	else
	{
		// Kode lain
	}
}
```
