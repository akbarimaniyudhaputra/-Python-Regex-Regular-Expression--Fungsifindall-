
# Python - Regex (Regular Expression) - Fungsi findall()

## Fungsi findall()
 - ketikkan import re untuk menggunakan library/modul regular expression
 - Berfungsi untuk mencari berbagai substring di dalam string dengan pola tertentu 
 - Hasil/outputnya berupa list 
 - Mencari pola tulisan X di field/kolom X menggunakan fungsi findall()
 - str adalah untuk mengubah tipe data menjadi string
 - parameter flags=re.IGNORECASE artinya untuk mengabaikan case atau huruf kapital/kecil
 - .to_string() menjadikan tipe datanya berbentuk string
 - data.loc[10] untuk menampilkan data pada indeks ke-10
 
## Untuk lebih jelasnya dapat mengakses laman berikut
 - https://pandas.pydata.org/docs/reference/api/pandas.Series.str.findall.html

#### Perintah untuk Mencari Pola/Pattern Redmi & Vivo

```http
import pandas as pd
from pandas import ExcelFile

namaFile = "E:\dataset\smartphone.xlsx"
data = pd.read_excel(namaFile, sheet_name="Sheet1")

data
```

```http
data["nama produk"]
```

```http
import re 
s = data["nama produk"]
x = s.str.findall("redmi", flags=re.IGNORECASE)
print(x)
```

```http
import re
s = data["nama produk"]
s.str.findall("vivo", flags=re.IGNORECASE) #mengabaikan case
```

```http
data.loc[10] 
```

```http
import re
s = data["nama produk"].to_string()
x = re.findall("[a-z]*redmi", s, flags=re.IGNORECASE)
print(x)
```

```http
import re
s = data["nama produk"].to_string()
x = re.findall("[a-z]*redmi", s, flags=re.IGNORECASE)
df = pd.DataFrame(x)
print(df.to_string())
```

```http
import re
s = data["nama produk"].to_string()
x = re.findall("[v][i][v][o]?", s, flags=re.IGNORECASE)   
df = pd.DataFrame(x)
print(df.to_string())
```
![1 1](https://user-images.githubusercontent.com/86678205/155359627-ecc17c03-0c0b-4272-a35f-d63bd2ad6ba8.PNG)
##
![1 2](https://user-images.githubusercontent.com/86678205/155359677-88953316-3f4c-470d-a365-e42b5afc6fd3.PNG)
##
![1 3](https://user-images.githubusercontent.com/86678205/155359678-72cac347-ec94-4ebd-893a-85a958bdaf55.PNG)
##
![1 4](https://user-images.githubusercontent.com/86678205/155359680-2a8f2629-4475-4909-83c7-a69a34dc8ee9.PNG)
##
![1 5](https://user-images.githubusercontent.com/86678205/155359683-b00d2dea-353c-48ea-8734-8882558184d1.PNG)
##
![1 6](https://user-images.githubusercontent.com/86678205/155359685-d00f585a-e771-4660-b71a-dc784a45dd94.PNG)
##
![1 7](https://user-images.githubusercontent.com/86678205/155359686-4eaa1855-16a0-4702-aac9-3dac323ca98f.PNG)
##
![1 8](https://user-images.githubusercontent.com/86678205/155359687-fcb28f23-79d1-41de-b5d4-27f2a7057118.PNG)
##
![1 9](https://user-images.githubusercontent.com/86678205/155359689-c36a4124-3ff8-4219-bfd7-816d60614758.PNG)

#### Perintah untuk Mencari Pola/Pattern Kata yang tersusun dari 4 huruf dari huruf P,O,C,O
```http
import pandas as pd
from pandas import ExcelFile

namaFile = "E:\dataset\smartphone.xlsx"
data = pd.read_excel(namaFile, sheet_name="Sheet1")

data
```

```http
import re
s = data["nama produk"].to_string()
x = re.findall("[PoCo]{4}", s, flags=re.IGNORECASE) 
if (x):
    print("ada")
else:
    print("tidak ada")
```

```http
print(x)
```

```http
df = pd.DataFrame(x)
print(df.to_string())
```

```http
import re
s = data["nama produk"].to_string()
x = re.findall("[Oppo]{4}[-]{1}[A54]{3}", s, flags=re.IGNORECASE) 
print(x)
if (x):
    print("ada")
else:
    print("tidak ada")
```
![2 1](https://user-images.githubusercontent.com/86678205/155359814-a1b39b88-427a-477a-a3e4-1b9b06f4f9f8.PNG)
##
![2 2](https://user-images.githubusercontent.com/86678205/155359818-b8c6b8fb-4196-46c0-a76d-0f643d28adb1.PNG)
##
![2 3](https://user-images.githubusercontent.com/86678205/155359822-e5b34948-86d8-46bb-8242-30a9c98fd48a.PNG)
##
![2 4](https://user-images.githubusercontent.com/86678205/155359824-842b3412-6239-495f-b560-bd48bcf41232.PNG)
##
![2 5](https://user-images.githubusercontent.com/86678205/155359828-e3e34f05-6b46-45c0-bd23-f5863caf9c1d.PNG)
