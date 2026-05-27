# <h1 align="center">Laporan Praktikum Modul 10 - ... </h1>
<p align="center">[MuhammadFaizMaulana] - [109082500124]</p>

## Unguided 

### 1. [Soal]
#### soal1.go

```go
package main

import "fmt"

func main() {
	var berat [1000]float64
	var n int

	fmt.Scan(&n)

	for i := 0; i < n; i++ {
		fmt.Scan(&berat[i])
	}

	min := berat[0]
	max := berat[0]

	for i := 1; i < n; i++ {
		if berat[i] < min {
			min = berat[i]
		}

		if berat[i] > max {
			max = berat[i]
		}
	}

	fmt.Println(min, max)
}

```
### Output Unguided :

##### Output 
![Screenshot Output Unguided 1_1](https://github.com/mfaizmaulana20/109082500124_MuhammadFaizMaulana_Modul9/blob/main/modul%209/output/soal%201.png)
[Penjelasan: Program ini digunakan untuk mencari berat paling kecil dan paling besar dari sejumlah data yang dimasukkan pengguna. Pertama, pengguna memasukkan jumlah data berat (n), lalu program membaca semua nilai berat dan menyimpannya ke dalam array. Setelah itu, program menganggap data pertama sebagai nilai minimum dan maksimum sementara. Kemudian program mengecek satu per satu data berikutnya, jika ada nilai yang lebih kecil maka dijadikan minimum baru, dan jika ada yang lebih besar maka dijadikan maksimum baru. Di akhir proses, program menampilkan berat terkecil dan terbesar dari semua data yang telah dimasukkan.]

### 2. [Soal]
#### soal2.go

```go
package main

import "fmt"

func main() {
	var berat [1000]float64
	var totalWadah [1000]float64
	var x, y int

	fmt.Scan(&x, &y)

	for i := 0; i < x; i++ {
		fmt.Scan(&berat[i])
	}

	jumlahWadah := x / y
	if x%y != 0 {
		jumlahWadah++
	}

	indeks := 0

	for i := 0; i < jumlahWadah; i++ {
		total := 0.0

		for j := 0; j < y && indeks < x; j++ {
			total += berat[indeks]
			indeks++
		}

		totalWadah[i] = total
	}

	totalSemua := 0.0

	for i := 0; i < jumlahWadah; i++ {
		totalSemua += totalWadah[i]
	}

	rata := totalSemua / float64(jumlahWadah)

	for i := 0; i < jumlahWadah; i++ {
		if i > 0 {
			fmt.Print(" ")
		}
		fmt.Print(totalWadah[i])
	}

	fmt.Println()
	fmt.Println(rata)
}
```
### Output Unguided :

##### Output 
![Screenshot Output Unguided 1_2](https://github.com/mfaizmaulana20/109082500124_MuhammadFaizMaulana_Modul9/blob/main/modul%209/output/soal%202.png)
[Program ini digunakan untuk menghitung total berat di setiap wadah lalu mencari rata-ratanya. Awalnya pengguna memasukkan jumlah seluruh data berat (x) dan kapasitas isi tiap wadah (y). Setelah semua data berat dimasukkan ke array, program membagi data tersebut ke beberapa wadah sesuai kapasitas yang ditentukan. Setiap wadah akan menjumlahkan berat barang yang masuk ke dalamnya, lalu hasil total tiap wadah disimpan. Setelah semua wadah selesai dihitung, program menjumlahkan seluruh total wadah dan mencari nilai rata-ratanya. Terakhir, program menampilkan total berat masing-masing wadah dan rata-rata total berat semua wadah.]

### 3. [Soal]
#### soal3.go

```go
package main

import "fmt"

type arrBalita [100]float64

func hitungMinMax(arrBerat arrBalita, n int, bMin, bMax *float64) {
	*bMin = arrBerat[0]
	*bMax = arrBerat[0]

	for i := 1; i < n; i++ {
		if arrBerat[i] < *bMin {
			*bMin = arrBerat[i]
		}

		if arrBerat[i] > *bMax {
			*bMax = arrBerat[i]
		}
	}
}

func rerata(arrBerat arrBalita, n int) float64 {
	var total float64

	for i := 0; i < n; i++ {
		total += arrBerat[i]
	}

	return total / float64(n)
}

func main() {
	var data arrBalita
	var n int
	var min, max, rata float64

	fmt.Print("Masukan banyak data berat balita : ")
	fmt.Scan(&n)

	for i := 0; i < n; i++ {
		fmt.Printf("Masukan berat balita ke-%d: ", i+1)
		fmt.Scan(&data[i])
	}

	hitungMinMax(data, n, &min, &max)
	rata = rerata(data, n)

	fmt.Printf("Berat balita minimum: %.2f kg\n", min)
	fmt.Printf("Berat balita maksimum: %.2f kg\n", max)
	fmt.Printf("Rerata berat balita: %.2f kg\n", rata)
}


```
### Output Unguided :

##### Output 
![Screenshot Output Unguided 1_2](https://github.com/mfaizmaulana20/109082500124_MuhammadFaizMaulana_Modul9/blob/main/modul%209/output/soal%204.png)
[Program ini dipakai untuk mengolah data berat balita. Pengguna memasukkan jumlah data lalu mengisi berat tiap balita satu per satu. Setelah itu, program menghitung berat paling kecil, berat paling besar, dan rata-rata dari seluruh data yang dimasukkan. Proses mencari nilai minimum dan maksimum dilakukan di fungsi hitungMinMax, sedangkan perhitungan rata-rata dilakukan di fungsi rerata. Di akhir, hasilnya ditampilkan dalam satuan kilogram dengan format dua angka di belakang koma.]

