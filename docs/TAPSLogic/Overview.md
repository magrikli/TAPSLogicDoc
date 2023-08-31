# TAPSLogic

Bu belgede Parkule otomatik otopark sisteminin kontrol yazılımı olan `TAPSLogic` ile ilgili temel noktalar ele alınmaktadır.   

## TAPSMain.py
Ana program dosyasıdır. Bu dosya çalıştığında argümanlardan aldığı komutlarla konfigüre olur.

#### Program Argümanları:

* **`ProjectName`**: Projenin adı. Bu argüman veritabanından veri çekilirken gerekir.
* **`Mode`**: Programın çalışma modunu seçer
    * **`'Restore'`**: Veritabanının `Sqlite3` veritabanından `Docker`da kurulu `Postgresql` veritabanına aktarılarak restore edilmesini sağlar. 
    * **`'RestoreWithoutPallets'`**: Veritabanının `Sqlite3` veritabanından `Docker`da kurulu `Postgresql` veritabanına aktarılarak `Pallets` tablosu hariç olarak restore edilmesini sağlar. Palet yerleri eğer son yedeklemeden sonra değişti ise palet verilerinin bozulmasını engeller. 
    * **`'RestoreAndRun'`**: Veritabanının `Sqlite3` veritabanından `Docker`da kurulu `Postgresql` veritabanına aktarılarak restore edilmesini ve ardından çalıştırlmasını sağlar. 
  
        >***Önemli:*** Bu durumda program her çalıştırıldığında restore edeceği için sistem çalıştıktan sonraki konfigüreasyon değişklikleri silinecektir.

    * **`'Backup'`**: `Docker`da kurulu `Postgresql` üzerindeki veritabanını `Sqlite3` veritabanına yedekler. 
    * **`'Run'`**: `Docker`da kurulu `Postgresql` üzerindeki veritabanını kullanarak programı çalıştırır. 

* **`SimuMode`**: Sistemin simulasyon modunda çalışıp çalışmayacağını belirler. `True` yada `False` değerini alır.",
* **`Dockerized`**: Programın `Docker` üzerinden çalıştırılıp çalıştılmadığını belirtir. Eğer `Docker` üzerinden çalıştırılıyorsa program içinde bazı parametre değişklikleri yapılmaktadır. 
* **`LogsContainer`**: Logların tutulduğu veritabanının `Docker` konteyner ismi.
* **`LogsDB`**: `Docker`da bulunan `Postgresql` veritabanındaki Logs Şemasının ismi.
* **`LogsPort`**: `Docker`da bulunan `Postgresql` Logs veritabanının port numarası.
* **`CfgContainer`**: Konfigürasyonun bulunduğu veritabanının `Docker` konteyner ismi.
* **`CfgDB`**: `Docker`da bulunan `Postgresql` veritabanındaki Cfg Şemasının ismi.
* **`CfgPort`**: `Docker`da bulunan `Postgresql` Cfg veritabanının port numarası.
* **`WebSocketPort`**: Control Panel yada ekranlarla haberleşmede kullanılacak olan Websocket port numarası.
* **`RestorePath`**: `Restore` komutu kullanıldığında verilerin okunacağı `Sqlite3` dosyalarının bulunduğu yol.
* **`BackupPath`**: `Backup` komutu kullanıldığında verilerin yedekleneceği `Sqlite3` dosyalarının bulunduğu yol.

TAPSMain, Sistemin Control Panel ve diğer ekranlarla WebSocket haberleşmesini sağlayan `CPanelWSS` modülünü de çalıştırır.
