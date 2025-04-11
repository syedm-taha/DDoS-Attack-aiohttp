# DDoS-Attack-aiohttp
Bu proje aiohttp ve asyncio kullanarak Senkron veya Asenkron methodlarıyla belirtilen IP adresine veya Domaine DDoS testi yapmaya yarar.


## Önerilen Sistem Gereksinimleri

- Python: 3.9.18
- Bellek: 2 GB (Yanlızca bu projeye ayrılan bellek boyutu)


## Kurulum
```sh
pip install -e .
```

*veya*

(önerilen)
```sh
pip install poetry
```
```sh
poetry install
```


## Başlat

```sh
python.main.py
```

*veya*

```sh
poetry run python main.py
```


## Bilgilendirme

Projede Senkron methodu için 4000 thread, Asenkron methodu için 8000 en yüksek eş zamanlı iş parçacığı ayarlanmıştır. Bu değerleri ihtiyacınıza göre ayarlayabilirsiniz. Daha yüksek değerler DDoS gönderilen hedefi daha fazla strese sokar fakat çok daha fazla bellek tüketir. Değerli ayarlamak için main.py dosyasında belirtilmiş alanları değişirebilirsiniz.

*Senkron İçin Thread Sayısı*
```python
def send():
session = requests.Session()
thread_count = 4000 # Thread Sayısı
```

ve

*Asenkron İçin Eş Zamanlı İş Parçacığı Sayısı*
```python
async with aiohttp.ClientSession() as session:
tasks = []
concurrency = 8000  # En yüksek eşzamanlı görev sayısı
```

-

*Node.js K6 versiyonunu repolarımda bulabilirsiniz. Bundan çok daha güçlüdür.*

-

# ⚠️ ÖNEMLİ UYARI:
Bu proje sunucu altyapılarının dayankıklılığını test etmek için oluşturulmuştur. Kullanıcı tarafından yapılan herhangi bir yasadışı saldırıdan tarafımız sorumlu değildir!
