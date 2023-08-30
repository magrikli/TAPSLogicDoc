# TAPSLogic

Bu belgede Parkule otomatik otopark sisteminin kontrol yazılımı olan `TAPSLogic` ile ilgili temel noktalar ele alınmaktadır.   

## TAPSMain.py
Ana program dosyasıdır. Bu dosya çalıştığında argümanlardan aldığı komutlarla konfigüre olur.

#### Program Argünamanları:

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

## Diğer Bileşenler

### [CPanelWSS](CPanelwss.md)
TAPSMain, Sistemin Control Panel ve diğer ekranlarla WebSocket haberleşmesini sağlayan `CPanelWSS` modülünü de çalıştırır.



# TAPSLogic aşağıdaki şekilde kurgulanmıştır:


TFacility nesnesi, tesise ait tüm bileşen, fonksiyon ve özellikleri barındırır.
Bu nesne tesiste bulunan otopark sistemlerinin yanı sıra, bariyerler, displayler, otopark yönetim sistemi gibi diğer bileşenleri de yönetir. 

```python
class TFacility:
    def __init__(self, ASimu):
        self.__Simu = ASimu
        self.EntranceCHCat = TCHCat.EmptyPallet
        self.EntranceCardNo = None
        self.Systems = {}
        self.Rec = {}
        self.PermittedCards = {}
        self.ServiceMails = {}
        self.SafetyOPC = None
        self.OPCActive = False
        self.Loading = True
        #LoadCompsFromDB(self)
        InitFacilityFromDB(self)
        self.Rec["Simu"]={"Value" : ASimu}
        self.Rec["OPCDataFlows"]={"Value" : False}
        self.__Hostname = self.Rec["Hostname"]["Value"]
        self.__SystemNo = self.Rec["SystemNo"]["Value"]
        self.__AssignedEntrance = self.Rec["AssignedEntrance"]["Value"]
        self.__PMSListenPort = self.Rec["PMSListenPort"]["Value"]
        self.__FacilityOPCPath = self.Rec["FacilityOPCPath"]["Value"]
        self.__CarWaitingEntryAtLoopTimeOut = self.Rec["CarWaitingEntryAtLoopTimeOut"]["Value"]
        self.__IgnoreServiceDoors = self.Rec["IgnoreServiceDoors"]["Value"]
        self.__LogLevel = self.Rec["LogLevel"]["Value"]
        self.__Operator = self.Rec["Operator"]["Value"]
        self.__PublicUse = self.Rec["PublicUse"]["Value"]
        self.__LPRPort = self.Rec["LPRPort"]["Value"]
        self.__DoorOpenCloseTimeOut = self.Rec["DoorOpenCloseTimeOut"]["Value"]
        self.__OpenDoorAtDelivery = self.Rec["OpenDoorAtDelivery"]["Value"]
        self.__CarExistsControl = self.Rec["CarExistsControl"]["Value"]
        self.__CarWaitingGeneralTimeOut = self.Rec["CarWaitingGeneralTimeOut"]["Value"]
        self.__ProjectName = self.Rec["ProjectName"]["Value"]
        self.__CardReaderPort = self.Rec["CardReaderPort"]["Value"]
        self.__FacilityOPCIP = self.Rec["FacilityOPCIP"]["Value"]
        self.__DBVersion = self.Rec["DBVersion"]["Value"]
        self.__DoorOpenAtWaitForEntry = self.Rec["DoorOpenAtWaitForEntry"]["Value"]
        self.__LPRListenPort = self.Rec["LPRListenPort"]["Value"]
        self.__StartTime = self.Rec["StartTime"]["Value"]
        self.__DynamicHeightWhenTurning = self.Rec["DynamicHeightWhenTurning"]["Value"]
        self.__FacilityName = self.Rec["FacilityName"]["Value"]
        self.__RemoteExists = self.Rec["RemoteExists"]["Value"]  
        self.__Owner = self.Rec["Owner"]["Value"]
        self.__ServiceDoorCount = self.Rec["ServiceDoorCount"]["Value"]
        self.__EntryAtLoop = self.Rec["EntryAtLoop"]["Value"]
        self.__CloseSystemsToBalance = self.Rec["CloseSystemsToBalance"]["Value"]
        self.__CapacityVariance = self.Rec["CapacityVariance"]["Value"]
        self.__PMSIP = self.Rec["PMSIP"]["Value"]
        self.__PMSPort = self.Rec["PMSPort"]["Value"]
        self.__MaxClosedSystems = self.Rec["MaxClosedSystems"]["Value"]
        self.__CommonLogicVersion = self.Rec["CommonLogicVersion"]["Value"]
        self.__ConveyorLogicVersion = self.Rec["ConveyorLogicVersion"]["Value"]
        self.__LiftLogicVersion = self.Rec["LiftLogicVersion"]["Value"]
        self.__RoomLogicVersion = self.Rec["RoomLogicVersion"]["Value"]
        self.__ShelfLogicVersion = self.Rec["ShelfLogicVersion"]["Value"]
        self.__ShuttleLogicVersion = self.Rec["ShuttleLogicVersion"]["Value"]
        self.__TurntableLogicVersion = self.Rec["TurntableLogicVersion"]["Value"]
        self.__SafetyLogicVersion = self.Rec["SafetyLogicVersion"]["Value"]
        self.__FacilityEMGCount = self.Rec["FacilityEMGCount"]["Value"]
        self.__ConfirmMethod = self.Rec["ConfirmMethod"]["Value"]
        self.__EntryPerExit = self.Rec["EntryPerExit"]["Value"]
        self.__ServiceEmail = self.Rec["ServiceEmail"]["Value"]
        self.__EmailPwd = self.Rec["EmailPwd"]["Value"]

        self.Loading = False
        self.UDPClient = None
        self.LastCardReadTime = datetime.now()
        self.ConfigVerified = False
        self.FPLCRec = {"DriveCount": 0, "Id": 0, "SafetyNVLIndex": 0, "IP": self.FacilityOPCIP, "OPCPath": self.FacilityOPCPath}
        self.SafetyOPC = TOPCComp(TSysPLC(None, self.FPLCRec), "Safety_Control", self.OPCActive, self, None, self.Subscriber)
        self.Handler = self.TFacilityHandler(self)
        self.SafetyOPC.Handler = self.Handler
        self.SafetyOPC.ConfigPLC = self.ConfigFacilitySafetyPLC

        self.DoNextThread = threading.Thread(target=self.__DoNextTimer, name='DONextTimer', args=[self, ], daemon=True)
        self.__AMCHCatBarrier = 0
        self.Rec["Version"] = {"Value":GO.Version,"Group":"Info","Order":1, "DataType":"text"}
        self.Rec["IsOPCActive"] = {"Value":self.SafetyOPC.IsOPCActive,"Group":"Info","Order":2, "DataType":"text"}
        self.Rec["Simu"] = {"Value":self.__Simu,"Group":"Info","Order":3, "DataType":"text"}
        self.Rec["AMCHCatBarrier"] = {"Value":0,"Group":"Info","Order":4, "DataType":"text"}
        self.Rec["OPCCounter"] = {"Value":self.SafetyOPC.OPCCounter,"Group":"Info","Order":5, "DataType":"text"}

        self.ExitProgram = False
        self.AMCHCat = TCHCat.EmptyPallet
```
For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

### Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
