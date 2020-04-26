# 4queen_CSP

Pendekatan yang diperlukan yaitu dengan menempatkan ratu satu per satu di kolom yang berbeda, mulai dari kolom paling kiri. Ketika ratu dalam sebuah kolom, maka diperiksa terlebih dahulu apakah terdapat bentrokan dengan ratu yang sudah ditempatkan. Di kolom saat ini, jika baris yang ditempati tidak ada bentrokan, maka baris dan kolom tersebut ditandai sebagai bagian dari solusi. Jika tidak ditemukan baris seperti baris yang dimaksudkan karena adanya bentrokan, maka akan dilakukan algoritma backtracking dan me-return false.
Berikut adalah fungsi utama untuk mengcek peletakan ratu pada papan catur
```
// Function to check queens placement 
void nQueens (int k, int n){ 

	for (int i = 1;i <= n;i++){ 
		if (canPlace(k, i)){ 
			arr[k] = i; 
			if (k == n){
				display(n); 	
			}
			else{
				nQueens(k + 1, n); 
			}
		} 
	} 
} 
```

Pada fungsi diatas, dipanggil fungsi canPlace, yang isinya berupa:
```
bool canPlace (int k, int i){ 
	for (int j = 1;j <= k - 1;j++){ 
		if (arr[j] == i || 
			(abs(arr[j] - i) == abs(j - k))){
				return false; 	
			}
	} 
	return true; 
} 
```
Intinya dicek apakah ratu dapt diletakkan tanpa bertabrakan.






Kemudian terakhir ada fungsi untuk menampilkan hasilnya:
```
// Function to display placed queen 
void display (int n){ 
	cout << "\n---------------------------------\n";
	cout << "Arrangement No. " << ++no; 
	cout << "\n---------------------------------\n"; 

	for (int i = 1; i <= n; i++){ 
		for (int j = 1; j <= n; j++){ 
			if (arr[i] != j) 
				cout << "\t_"; 
			else
				cout << "\tQ"; 
		} 
		cout << endl; 
	} 

	cout << "\n---------------------------------\n"; 
} 
```
Pada Source Code saya, jumlah catur pada fungsi main saya set sebanyak 4 buah
