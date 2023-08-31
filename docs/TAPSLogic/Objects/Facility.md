
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