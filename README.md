<div align="center" style="padding-bottom: 10px">
<h1>🔖TUGAS-7: Elemen Dasar Flutter🔖</h1>
</div>

<h3> Nama	: Febi Claudia Damanik </h3>

<h3> NPM	: 2106751884 </h3>

<h3> Kelas 	: D </h3>

# 💫Stateless widget dan stateful widget💫
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
		<td>Memiliki state, cocok untuk menyusun widget dengan pengolahan data yang interaktif</td>
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

# 👷‍♀️Widget yang digunakan di proyek serta fungsinya👷‍♀️
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
- Dalam hal ini, saat tombol + _(increment)_ diklik terdapat pemanggilan fungsi `setState()`
- Method `_incrementCounter` akan dijalankan `onPressed: _incrementCounter` untuk menambahkan variabel counter sebanyak satu satuan.
- Dalam hal ini, saat tombol - _(decrement)_ diklik terdapat pemanggilan fungsi `setState()`
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
		<td>Pada saat kompilasi berjalan, nilai dari variabel belum diketahui secara langsung, variabelnya sudah di inialisiasi namun nilainya akan didapatkan saat kompilasi dijalankan</td>
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
- Membuat `if conditional` apabila counter 0 agar button minus menghilang sementara selain dari itu tombol yang ditampilkan adalah tombol + dan -.
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


<div align="center" style="padding-bottom: 10px">
<h1>🔖Tugas 8: Flutter Form🔖</h1>
</div>

<h3> Nama	: Febi Claudia Damanik </h3>

<h3> NPM	: 2106751884 </h3>

<h3> Kelas 	: D </h3>

# ⚜Navigator.push dan Navigator.pushReplacement⚜
🧭‣ Navigator.push

➔ Navigator.push adalah suatu metode yang digunakan untuk menambahkan route lain ke atas tumpukan screen saat ini dimana halaman baru ditampilkan di atas halaman sebelumnya.

🧭‣ Navigator.pushReplacement

➔ Navigator.pushReplacement adalah suatu metode yang digunakan untuk memindahkan atau mengubah route pada navigator yang terikat pada context yang bersangkutan dengan melakukan push page baru dan menghapus atau menghilangkan page/routing lama atau yang sebelumnya digunakan.

<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
</head>
<body> 
 <table>
 <tr>
 	<td align="center">🎇Perbedaan antara Navigator.push() dan Navigator.pushReplacement()🎇</td>
<tr>
<td>Navigator.push() hanya melakukan penambahan route pada stack dan memindahkan ke page baru tersebut, tetapi tidak menghilangkan page/route yang lama. Berbeda halnya dengan Navigator.pushReplacement() akan memindahkan page/route ke page/route baru dan menghilangkan page/route yang lama sehingga tidak dapat berpindah ke halaman sebelumnya.</td>
</tr>
	 
</table>

</body>
</html>

# 👷🏻‍♀️Widget yang digunakan di proyek beserta fungsinya👷🏻‍♀️
◽ `Card` → Mengatur info terkait menjadi title, subtitle, dan leading ke dalam kotak dengan sudut membulat dan efek bayangan di tepi

◽ `Drawer` → Membuat fitur navigasi menuju page lain berupa drawer di sisi kiri layar

◽ `DropdownButton` → Menampilkan objek berupa pemilihan opsi dalam fitur dropdown

◽ `Dialog` → Menampilkan pop up window pada halaman aplikasi
	
◽ `Expanded` → Mengatur ukuran *child* widgetnya mengisi tempat yang tersedia
	
◽ `Form` → Menyisipkan fitur Form yang menerima input dari pengguna

◽ `ListView` → Menampilkan widget-widget lain yang menjadi *child*-nya

◽ `Padding` → Mengatur padding pada widget yang menjadi *child*-nya

◽ `SizedBox` → Mengatur jarak antara satu widget dengan widget lain

◽ `TextButton` → Menyisipkan sebuah button yang dapat diberi tulisan untuk menampilkan date picker dan submit form
	
◽ `TextFormField` → Menyisipkan objek berupa input name dan amount sebagai field bagi pengguna untuk memasukkan teks

# ⛲Jenis-jenis event yang ada pada Flutter⛲
🔹 onTap: event yang terjadi ketika widget di-tap.

🔹 onFocusChange: pemanggilan properti function saat fokus berubah.

🔹 onPressed: pemanggilan properti function dimana terdapat event yang di-trigger ketika sebuah tombol ditekan, biasanya ada pada widget jenis Button.

🔹 onSaved: pemanggilan properti function dimana terdapat event yang di-trigger ketika sebuah form disimpan, biasanya ada pada widget jenis input/form.

🔹 onChanged: pemanggilan properti function dimana terdapat event yang di-trigger ketika terjadi sebuah perubahan pada sebuah widget, biasanya ada pada widget jenis input/form.

# 🌐Cara kerja Navigator dalam "mengganti" halaman🌐
Navigator adalah salah satu widget yang berfungsi menampilkan konten ke halaman atau layar baru. Pada saat pengimplementasian navigasi halaman pada Flutter memanfaatkan struktur data stack. Dalam hal ini, biasanya widget Navigator di Flutter digunakan untuk mempertahankan tumpukan stack dan berperan dalam mengatur stack of route. Method yang digunakan pada objek Navigator, seperti:
- `Method push` untuk menimpa halaman sebelumnya.
- `Method pop` untuk kembali ke halaman sebelumnya dengan menghapus halaman sekarang.
- `Method pushReplacement` akan mengganti halaman yang baru dan pop untuk kembali ke halaman sebelumnya dengan menghapus halaman sekarang. 

Dengan demikian, pengguna dapat berpindah pada halaman sebelumnya dengan operasi ini.

# 📌Pengimplementasian checklists dari tasks📌
- Menambahkan file `budget.dart`, `data.dart`, `drawer.dart`, dan `form.dart` pada folder `lib`.

- Menambahkan tiga tombol navigasi pada drawer/hamburger untuk ke halaman counter, halaman form, dan halaman yang menampilkan data budget yang telah di-input melalui form pada file `drawer.dart`.

```Dart
  Widget buildMenuItems(BuildContext context) => Container(
      padding: const EdgeInsets.all(24),
      child: Wrap(
        runSpacing: 12,
        children: [
          ListTile(
            title: const Text('counter_7'),
            onTap: () {
              // Route menu ke halaman utama
              Navigator.of(context).pushReplacement(
                  MaterialPageRoute(builder: (context) => const MyHomePage()));
            },
          ),
          ListTile(
            title: const Text('Tambah Budget'),
            onTap: () {
              // close navigation drawer before
              Navigator.pop(context);
              // Route menu ke halaman form
              Navigator.of(context).push(
                MaterialPageRoute(builder: (context) => const MyFormPage()),
              );
            },
          ),
          ListTile(
            title: const Text('Data Budget'),
            onTap: () {
              // close navigation drawer before
              Navigator.pop(context);
              // Route menu ke halaman data budget
              Navigator.of(context).push(
                MaterialPageRoute(builder: (context) => const MyDataPage()),
              );
            },
          ),
        ],
      ));
}
```

- Membuat widget Drawer di file `drawer.dart` yang berisi tombol navigasi untuk ke halaman counter_7, Tambah Budget, dan Data Budget yang menampilkan data yang telah dimasukkan oleh user di halaman form. Widget Drawer ini diimplementasikan menggunakan stateless widget.

- Menambahkan models pada file baru `budget.dart` dimana terdapat inisialisasi array list budgets.

```Dart
class Budget {
  static List<Budget> budgets = [];
  String name;
  int amount;
  String type;
  DateTime date;

  Budget({
    required this.name,
    required this.amount,
    required this.type,
    required this.date,
  });

  static void addBudget({
    required name,
    required amount,
    required type,
    required date,
  }) {
    budgets.add(Budget(
      name: name,
      amount: amount,
      type: type,
      date: date,
    ));
  }
}
```

- Menambahkan file baru `data.dart` untuk menampilkan data budget yang telah di-input melalui form dan disimpan dalam array list budgets.

- Menambahkan file baru `form.dart` untuk membuat Form dan Elemen Input. Di halaman form, terdapat widget input name, amount, type, date, dan button untuk submit form.

- Membuat tombol yang menyimpan data tersebut di dalam array list budgets setelah ditekan.

- Menjalankan proyek program Flutter dengan `flutter run` pada `cmd`.

- Melakukan `add-commit-push` proyek ke repositori `pbp-flutter-lab`.

**◻Tambahan Implementasi Bonus◻**

◽ ✅ Menambahkan elemen date picker pada halaman form.

```Dart
    TextButton(
      onPressed: (() {
	showDatePicker(
	  context: context,
	  initialDate: DateTime.now(),
	  firstDate: DateTime(2000),
	  lastDate: DateTime(2999),
	).then((value) {
	  setState(() {
	    _date = value;
	  });
	});
      }),
```

◽ ✅ Menampilkan elemen date (format bebas) pada setiap elemen budget yang ada pada halaman data budget.

```Dart
  child: ListTile(
      title: Text("${budget.name}\n${budget.amount}"),
      subtitle: Text(budget.date.toString().split(' ')[0]),
      trailing: Text(budget.type)),
);
}).toList(),
```

◽ ✅ Refactor widget Drawer ke sebuah file terpisah.

```Dart
Widget build(BuildContext context) => Drawer(
      child: SingleChildScrollView(
        child: Column(
           crossAxisAlignment: CrossAxisAlignment.stretch,
            children: <Widget>[
              buildMenuItems(context),
            ]),
      ),
    );
```

<div align="center" style="padding-bottom: 10px">
<h1>🔖Tugas 9: Integrasi Web Service pada Flutter🔖</h1>
</div>

<h3> Nama	: Febi Claudia Damanik </h3>

<h3> NPM	: 2106751884 </h3>

<h3> Kelas 	: D </h3>

# 💾Pengambilan data JSON💾
💢‣ Apakah bisa kita melakukan pengambilan data JSON tanpa membuat model terlebih dahulu?

➔ Bisa, pengambilan data JSON tanpa membuat model akan dikirimkan sebagai HTTP Response dalam bentuk raw data. Pengimplementasiannya dapat dilakukan dengan menggunakan `jsonDecode()` *import* dari `dart:convert`. 

💢‣ Jika iya, apakah hal tersebut lebih baik daripada membuat model sebelum melakukan pengambilan data JSON?

➔ Pengambilan data JSON tanpa membuat model terlebih dahulu dapat membuat *developer* sulit untuk melihat dan mengakses data tersebut. Dalam hal ini, pembuatan model diperlukan agar *developer* lebih mudah untuk melakukan operasi pada HTTP Response tersebut dengan mengubahnya menjadi dart object. Dengan begitu, sebaiknya pembuatan model dalam pengambilan data JSON dilakukan agar representasi data lebih terstruktur dan efisien. 

# 🐱‍💻Widget yang digunakan di proyek beserta fungsinya🐱‍💻
Berikut tambahan widget baru yang digunakan di proyek Tugas 9, yaitu :

◽ `Checkbox` → Menampilkan *checkbox* untuk memberi pilihan kepada *user*.

◽ `ElevatedButton` → Membuat *button* memiliki *shadow* dan terlihat menonjol dibandingkan dengan elemen-elemen lainnya dengan desain material Elevation.

◽ `FutureBuilder` → Menampilkan data yang akan diambil dari *web service* yang mendukung proses asinkron.

◽ `Flexible` → Mengatur turunan *widget* agar tampilannya dapat diatur dan bersifat fleksibel pada halaman detail.

◽ `RichText` → Menampilkan teks yang menerapkan beberapa *style* yang bervariasi.

◽ `TextSpan` → Menampung beberapa properti berupa *style* dan spesifikasi *style* lainnya untuk teks pada halaman detail.

# 💱Mekanisme pengambilan data dari JSON💱
🔸 Mendefinisikan model *class* sesuai dengan *response data* yang akan diambil ketika melakukan pemanggilan *web service*.

🔸 Membuat fungsi untuk melakukan *fetching* data dari *web service* kemudian mengiterasi serta menampilkan setiap data ke aplikasi dengan memanfaatkan `FutureBuilder`.

🔸 Setiap data di-*fetch* melalui HTTP GET *request* yang melakukan pengambilan data dari URL yang diinginkan dan mengembalikan sebuah response dengan menggunakan metode `http.get`.

🔸 *Response* tersebut akan dikonversi menjadi Dart object. Untuk setiap object tersebut akan dilakukan looping dan disimpan pada sebuah list. Selain itu, iterasi dari list tersebut digunakan untuk menampilkan data pada flutter.

# 📌Pengimplementasian checklists dari tasks📌
- Melakukan refactor file di dalam folder `lib` dengan membuat 3 (tiga) folder baru dengan nama `model`, `page`, dan `utility`. Proses ini dilakukan untuk meningkatkan keterbacaan, mengurangi kompleksitas kode, dan memudahkan proses `maintenance` ke depannya.

- Memindahkan file `data.dart` dan `form.dart` ke dalam ke folder `page`, file `budget.dart` dipindahkan ke dalam folder `model`, dan `drawer.dart` dipindahkan ke dalam folder `utility`.

- Membuat file baru pada folder `lib/model` dengan nama `mywatchlist.dart` berisi model MyWatchList yang disesuaikan dengan data JSON dari *web service*. Selain itu, menambahkan *keyword* `required` pada setiap parameter model pada bagian constructor.

- Melakukan `flutter pub add http` pada terminal proyek Flutter untuk menambahkan package `http`.

- Menambahkan kode berikut untuk memperbolehkan akses Internet pada aplikasi Flutter yang sedang dibuat pada file `android/app/src/main/AndroidManifest.xml`.

- Membuat file baru pada folder `utility` dengan nama `fetch.dart` untuk melakukan pengambilan data dari URL http://tugas2-pbp-febidamanik.herokuapp.com/mywatchlist/json/ menggunakan metode `http.get`.

- Membuat file baru pada folder `page` dengan nama `mywatchlist_page.dart` untuk menampilkan seluruh *title* dari objek MyWatchList pada halaman `My Watch List`.

- Membuat file baru pada folder `page` dengan nama `mywatchlist_detail.dart` untuk menampilkan halaman detail untuk setiap mywatchlist yang ada pada daftar tersebut. Setiap detail akan menampilkan *release data*, *rating*, *status*, dan *review*.

- Membuat halaman detail film dengan menggunakan `FutureBuilder` untuk menampilkan data yang telah dikonversi ke aplikasi.

- Menambahkan kode berikut untuk menambahkan menu `My Watch List` pada file `drawer.dart` yang telah dibuat di bawah menu ListTile Data Budget.

- Menambahkan tombol navigasi baru pada setiap film di halaman `My Watch List` yang akan mengarah ke halaman detail film jika diklik dengan bantuan widget ListTile dan *event handler* `onTap()` yang akan melakukan operasi `Navigator.push`.

- Melakukan *restart* aplikasi dengan menekan tombol `r` pada terminal di tempat menjalankan Flutter.

- Menjalankan proyek program Flutter dengan `flutter run` pada `cmd`.

- Melakukan `add-commit-push` proyek ke repositori `pbp-flutter-lab`.

**◻Tambahan Implementasi Bonus◻**

◽ ✅ Menambahkan *checkbox* dengan widget CheckboxListTile untuk menandakan film tersebut sudah ditonton atau belum. 

◽ ✔ Dengan menggunakan *event handler*, yaitu `onChanged()` akan melakukan operasi `setState()` untuk mengubah status ditonton yang dapat bernilai `true` atau `false` pada saat *checkbox* ditekan.

◽ ✅ Menambahkan warna untuk *outline* pada setiap *mywatchlist* pada halaman *mywatchlist* berdasarkan status ditonton dua pilihan warna untuk status yang bernilai `true` akan berwarna `Colors.lightGreenAccent.shade400` sedangkan untuk status yang bernilai `false` `Colors.redAccent.shade400`.

◽ ✔ Mengimplementasikan Card makeCard yang berisi data MyWatchList dan mengatur pewarnaan pada setiap *outline* sesuai dengan status film yang ditonton.

◽ ✅ *Refactor* function *fetch* data dari *web service* ke sebuah file terpisah.

◽ ✔ Membuat folder serta file baru, yaitu folder `utility` dan file `fetch.dart` serta menambahkan *import* pada file yang membutuhkan untuk melakukan *fetching* data dari *web service* kemudian menampilkannya ke aplikasi yang telah dibuat sebelumnya.
