<div align="center" style="padding-bottom: 10px">
<h1>🔖TUGAS-7: Elemen Dasar Flutter🔖</h1>
</div>

<h3> Nama	: Febi Claudia Damanik </h3>

<h3> NPM	: 2106751884 </h3>

<h3> Kelas 	: D </h3>

# 🔍Stateless widget dan stateful widget🔍
✨‣ Stateless _widget_

➔ Stateless _widget_ adalah _widget_ statis dimana seluruh konfigurasi yang dimuat didalamnya telah diinisiasi sejak awal dan tidak dapat diubah setelah widget tersebut dibuat. Contoh : IconButton dan Text

✨‣ Stateful _widget_

➔ Stateful _widget_ adalah _widget_ dinamis sehingga _widget_ ini dapat diperbaharui kapanpun dibutuhkan berdasarkan user actions atau ketika terjadinya perubahan data. Contoh : CheckBox dan Form

Berikut tabel yang menampilkan perbedaan antara keduanya.
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
</head>
<body> 
 <table>
 <tr>
 		<td>📴Stateless widget</td>
 		<td>📱Stateful widget</td>
 <tr>
 		<td>Bersifat statis (tidak berubah)</td>
 		<td>Bersifat dinamis (dapat berubah)</td>
  <tr>
		<td>Tidak memiliki state, cocok untuk wigdet tanpa perubahan data</td>
		<td>Memiliki state, cocok untuk menyusun _widget_ dengan pengolahan data yang interaktif</td>
  <tr>
		<td>Cara kerja dengan konsep Constructor🠚Build</td>
		<td>Cara kerja dengan konsep Constructor🠚Internal State🠚Build</td>
  <tr>
		<td>Lebih efisien waktu eksekusinya</td>
		<td>Memerlukan waktu reload render</td>
  <tr>
		<td>Contoh : Widget yang berisi text “You have clicked the button this many times : 1”, maka text selalu menjadi “You have clicked the button this many times : 1</td>
		<td>Contoh : Widget yang berisi text “You have clicked the button this many times : 1”, maka di stateful widget kita dapat merubah text tersebut sesuai kebutuhan</td>
   </tr>
	 
 </table>

</body>
</html>

# 👷‍♀️Widget yang digunakan di proyek beserta fungsinya👷‍♀️
◽ `MaterialApp` → Mengatur segala route dan theme dari aplikasi

◽ `Appbar` → Menampilkan title dan item menu item pop up berserta aksi nya

◽ `Row` → Menampilkan widget dari halaman secara horizontal
	
◽ `Column` → Mengatur layout _widget_ di dalamnya secara menurun atau vertical
	
◽ `FloatinActionButton` → Menampilkan tombol icon yang event-nya dapat dimodifikasi
	
◽ `Icon` → Menampilkan icon yang dibutuhkan sesuai propertinya
	
◽ `Spacer` → Mengatur jarak antar _widget_
	
◽ `Text` → Menyisipkan sebuah teks 
	
◽ `Center` → Mengatur layout _widget_ di dalamnya agar rata tengah
	
◽ `Scaffold` → Mengatur layout dari _widget_ utama

# 🧮Fungsi dari setState()🧮
Pemanggilan fungsi `setState()` berfungsi untuk memberitahu _widget_ bahwa ada objek yang berubah pada State sehingga aplikasi akan memanggil method build() serta memuat ulang _widget_ tersebut dengan nilai yang sudah diubah. Variabel yang dapat terdampak adalah variabel/data yang di-pass sebagai argumen pada inner function setState().
Pada aplikasi counter_7, fungsi setState() berpengaruh pada variabel counter.
- Dalam hal ini, saat tombol + (increment) diklik terdapat pemanggilan fungsi `setState()`
- Method `_incrementCounter` akan dijalankan `onPressed: _incrementCounter` untuk menambahkan variabel counter sebanyak satu satuan.
- Dalam hal ini, saat tombol - (decrement) diklik terdapat pemanggilan fungsi `setState()`
- Method `_decrementCounter` akan dijalankan `onPressed: _decrementCounter` untuk mengurangi variabel counter sebanyak satu satuan.

# 📊Perbedaan antara const dengan final📊
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
</head>
<body> 
 <table>
 <tr>
 		<td>📤Const</td>
 		<td>📥Final</td>
 <tr>
 		<td>Dapat diinsiasi ulang sesuai nilainya (fleksibel) setiap dilakukan render</td>
 		<td>Tidak dapat inisialisasi ulang sehingga variabel bernilai tetap dari awal deklarasi</td>
  <tr>
		<td>Pada saat kompilasi berjalan, nilai dari variabel tersebut harus sudah diberikan value secara langsung</td>
		<td>Pada saat kompilasi nilai variabel belum diketahui secara langsung, variabelnya sudah di inialisiasi namun nilainya akan didapatkan saat kompilasi dijalankan</td>
  <tr>
		<td>
		void main() {
  		const tasks = 6;
  		print(tasks);
		}</td>
		<td>
		void main() {
  		final tasks = 6;
  		print(tasks);
		}</td>
	 
</table>

</body>
</html>

# 📌Pengimplementasian checklists dari tasks📌
- Membuat aplikasi Flutter bernama counter_7
``` 
flutter create counter_7
cd counter_7
```
- Mengubah title `Flutter Demo Home Page` menjadi `Program Counter`
```dart
home: const MyHomePage(title: 'Program Counter'),
 ```
- Membuat variabel pembantu di dalam function build
```dart
int _counter = 0;
```
- Membuat button plus sebagai tombol + _(increment)_ menambahkan angka sebanyak satu satuan.
```dart
void _incrementCounter() {
    setState(() {
      // This call to setState tells the Flutter framework that something has
      // changed in this State, which causes it to rerun the build method below
      // so that the display can reflect the updated values. If we changed
      // _counter without calling setState(), then the build method would not be
      // called again, and so nothing would appear to happen.
      _counter++;
    });
  }
```
- Membuat button minus sebagai tombol - _(decrement)_ mengurangkan angka sebanyak satu satuan.
```dart 
void _decrementCounter() {
    setState(() {
      if (_counter > 0) {
        _counter--;
      }
    });
  }
```
- Mengatur teks indikator berubah menjadi "GANJIL" warna biru apabila counter bernilai ganjil.
```dart 
    ] else ...[
      const Text(
        'GANJIL',
        style: TextStyle(color: Colors.blue),
      )
    ],
```
- Mengatur teks indikator berubah menjadi "GENAP" warna merah apabila counter bernilai genap dimana angka 0 dianggap sebagai angka genap.
```dart 
  if (_counter % 2 == 0) ...[
    const Text(
      'GENAP',
      style: TextStyle(color: Colors.red),
    )
```

**◻Tambahan Implementasi Bonus◻**

◽ ☑ Menyembunyikan/menghilangkan tombol - apabila counter bernilai 0.
- Membuat `if conditional` apabila counter 0 agar button minus menghilang sementara selain dari itu tombol yang ditampilkan adalah tombol + dan -
```dart 
      floatingActionButton: Padding(
        padding: const EdgeInsets.only(left: 30.0),
        child: Row(mainAxisAlignment: MainAxisAlignment.center, children: [
          if (_counter != 0) ...[
            FloatingActionButton(
                onPressed: _decrementCounter,
                tooltip: 'Decrement',
                child: const Icon(Icons.remove))
          ],
          const Spacer(),
          FloatingActionButton(
              onPressed: _incrementCounter,
              tooltip: 'Increment',
              child: const Icon(Icons.add)),
        ]),
      ), // This trailing comma makes auto-formatting nicer for build methods.
    );
  }
}
```
