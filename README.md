
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
