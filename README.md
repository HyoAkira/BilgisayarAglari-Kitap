YAPILACAK DEĞİŞİKLİKLER
- Mbps ve Mbs gösteriminin farkındalığı için ekstra alan ekleme güzel olabilir. Ayrıca 1 tane paragrafta 10mb/s gibi bir yazı vardı onu anlam doğruluğu için değiştirmek gerekir.
- Birbiriyle çelişen 2 fotoğraf vardı Cat kabloların hızı ile ilgili bilgi konusunda.
- netstat ile ilgili yazının olduğu yerde meraklısına ekstra bilgi olması açısından yeni linux dağıtımlarında net-tools paketi artık geliştirilmediğinden dolayı eklenmiyor. iproute2 paketi ile birlikte gelen ss ve ip komutlarını kullanıyoruz. SS paketi netstat'ın karşılığı.
- Ağ çakışma alanları ile ilgili güzel bir video vardı, sorunun altına eklenebilir.
   >>> kendim için hatırlatma: router her port yayın alanı, switch her port çakışma alanı, hub bağlı tüm cihazlar tek çakışma alanı.

# Bilgisayar Ağları Ders Notları

**DİKKAT:** Henüz düzenleme aşaması devam etmektedir. Çok sayıda eksik ve hatalı kısımlar bulunmaktadır.
 
İçeriğin okunabilir hali için buraya bakabilirsiniz: https://ozalpmurat.github.io/BilgisayarAglari-Kitap/

İsterseniz, [buradan](https://ozalpmurat.github.io/BilgisayarAglari-Kitap/BilgisayarAglari-Murat%C3%96zalp.pdf) PDF biçiminde de indirebilirsiniz.

---
# Repoyu yerelde çalıştırmak için
Normalde bu sitede, Github Action kullanarak derleyip, github.io üzerinden görüntülüyoruz. Ancak Github action ücretsiz kullanımı ay içinde belirli süre ile sınırlı. Bu nedenle en ufak değişiklikte push edip action çalıştırmamak için, değişiklikleri önce yerelde izlemek isteyebilirsiniz.

Bunun için önce bir Python Virtual Environment oluşturun ki kuracağımız kütüphaneler bu izole ortamda kalsın, sistem kütüphanelerini karıştırmasın.

```sh
python -m venv env
cd env
source bin/activate
git checkout https://github.com/ozalpmurat/BilgisayarAglari-Kitap.git
cd BilgisayarAglari-Kitap
python -m pip install --upgrade pip
pip install -r requirements.txt
mkdocs build
mkdocs serve
```
Üsttekileri yapınca aşağıdaki gibi bir ekran geliyor. Son satırda yazan adresten web sitesini görüntüleyebilirsiniz.
```
...
INFO    -  Documentation built in 0.48 seconds
INFO    -  [12:49:54] Watching paths for changes: 'docs', 'mkdocs.yml'
INFO    -  [12:49:54] Serving on http://127.0.0.1:8000/BilgisayarAglari-Kitap/
```

**Markdown Docs** kullanımı için linkler:
- https://github.com/marketplace/actions/markdown-docs
- https://github.com/ldeluigi/markdown-docs
- https://pypi.org/project/mkdocs-with-pdf/
