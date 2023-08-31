## Component Alarms
### TRoomAlarm 
```python title="PLC Variable"
class TRoomAlarm(IntEnum):
    RoomEMGPressed = 1
    RoomNotConfigured = 2
    RoomEthercatCommError = 3
    TerminalEMGPressed = 4
    FlapInverterSafetyNotOK = 5
    FlapDriveError = 6
    NoServerConnection = 7
    TurntableIsNotInSafePositionWhenGointToRoom = 8
    CantMoveFlapsLiftIsUnsafePosition = 9
    RoomConfiguredButNoConveyorAssigned = 10
    ManuelAlarm = 11
    LiftNotUpdated = 12
    ShuttleNotUpdated = 13
    TTNotUpdated = 14
    ConveyorNotUpdated = 15
    SafetyUpdateError = 16

    Door1OpenTimeOut = 17
    Door1CloseTimeOut = 18
    Door2OpenTimeOut = 19
    Door2CloseTimeOut = 20

    FlapsNotConvenientButNoCommand = 21
    LeftFlapOpeningTimeOut = 22
    LeftFlapClosingTimeOut = 23
    RightFlapOpeningTimeOut = 24
    RightFlapClosingTimeOut = 25

    LBPalletLockOpenTimeOut = 26
    RBPalletLockOpenTimeOut = 27
    LFPalletLockOpenTimeOut = 28
    RFPalletLockOpenTimeOut = 29

    LBPalletLockCloseTimeOut = 30
    RBPalletLockCloseTimeOut = 31
    LFPalletLockCloseTimeOut = 32
    RFPalletLockCloseTimeOut = 33

    ERBoxSupplyFuse = 34
    FlapInverterCircuitBraker = 35
    Power12V_Fuse = 36
    Power24V_Fuse = 37
    PowerSupply = 38
    PowerOutletFuse = 39
    PalletLockLeftBackFuse = 40
    PalletLockLeftFrontFuse = 41
    PalletLockRightBackFuse = 42
    PalletLockRightFrontFuse = 43
    ERBoxUPSFuse = 44
    Door1Fault = 45
    Door2Fault = 46
```

### TConveyorAlarm
```python title="PLC Variable"
class TConveyorAlarm(IntEnum):
    ConveyorNotConfigured = 1
    ConveyorDriveError = 2
    EthercatCommError = 3
    FrontLockTimeOut = 4
    RearLockTimeOut = 5
    ManuelAlarm = 6
    GeneralAlarm = 7
    TransferTimeOut = 8
    RunningConditionNotOK = 9
    ShelfAlarm = 10
    ShelfNotUpdated = 11
    LiftNotUpdated = 12
    TurntableNotUpdated = 13
    ShuttleNotUpdated = 14
    RoomNotUpdated = 15
    ShelfGroupNotUpdated = 16
    SafetyUpdateError = 17
    ConveyorInverterSafetyNotOK = 18
    BrakeFuse = 19
    InverterCircuitBraker = 20
    ActiveConveyorNotUpdated = 21
    ActiveConveyorZero = 22
    ActiveConvyorNotMatching = 23
    RunningWhenIdle = 24
    PalletMovesWrongSideAuto = 25
    ManuelMoveRightWrongSensor = 26
    ManuelMoveRightWrongSide = 27
    ManuelMoveLeftWrongSensor = 28
    ManuelMoveLeftWrongSide = 29
    ManuelMoveLeftWrongSideShelf = 30
    ManuelMoveLeftWrongSideNoShelf = 31

    gaServiceDoorOpened = 47
    gaEMGPressed = 48
    gaEMGNotOK = 49
    gaNoCommonConfiguration = 50
    gaMotorContactorError = 51
    gaPLCSafetyUpdateError = 52
```

### TLiftAlarm
```python title="PLC Variable"
class TLiftAlarm(IntEnum):
    LiftPartsNotOK = 1
    EthercatCommError = 2
    FlapsConditionIsNotConvenientToRunTheLift = 3
    CentrifugeSwitchTriggered = 4
    MainMotorEMGTriggered = 5
    PitEMGTriggered = 6
    MainMotorInverterSafetyNotOK = 7
    LiftNotConfigured = 8
    LiftDriveError = 9
    NoServerConnection = 10
    ManuelAlarm = 11
    LiftIsOutOfRangeWhenRunning = 12
    LiftRunningConditionNotOk = 13
    ChainSensorNotOk = 14
    LiftSitTimeOut = 15
    GeneralAlarm = 16
    ModeOutofRange = 17
    EMGNotOK = 18
    PalletLockConditionIsNotConvenientToRunTheLift = 19
    RelatedCarrierNotUpdated = 20
    RoomNotUpdated = 21
    TopConveyorNotUpdated = 22
    SafetyUpdateError = 23

    CounterweightLowerLimit = 24
    CounterweightUpperLimit = 25
    LiftLowerLimit = 26
    LiftUpperLimit = 27
    LiftBoxSupplyFuse = 28
    MainMotorBrakeFuse = 29
    MainMotorInvertorCircuitBreaker = 30
    PowerSupply = 31
    ServiceMotorCircuitBreaker = 32
    UPSFuse = 33
    ShelfLocksAreOpen = 34

    RoomIsNotAuto = 35
    RoomNotSafeToMove = 36
    TopConveyorNotInAuto = 37
    TopConveyorNotIdleOrWaiting = 38
    PalletNotInLimits = 39
    CarWeightLimitExceeded = 40
    FacilityNotSafe = 41
    ShelvesNotSafe = 42
    RelatedCarriersNotSafe = 43

    gaServiceDoorOpened = 48
    gaEMGPressed = 49
    gaEMGNotOK = 50
    gaNoCommonConfiguration = 51
    gaPLCSafetyUpdateError = 52
```

### TShuttleAlarm
```python title="PLC Variable"
class TShuttleAlarm(IntEnum):
    ShuttleNotConfigured = 0
    RoomNotUpdated = 1
    TopConveyorNotUpdated = 2
    RelatedCarrierNotUpdated = 3
    ShuttleIsOutOfRangeWhenRunning = 4
    ShuttlePartsNotOK = 5
    RoomIsNotAuto = 6
    RoomNotSafeToMove = 7
    TopConveyorNotInAuto = 8
    TopConveyorNotIdleOrWaiting = 9
    PalletNotInLimits = 10
    CarWeightLimitExceeded = 11
    FacilityNotSafe = 12
    ShelvesNotSafe = 13
    RelatedCarriersNotSafe = 14
    ShuttleRunningConditionNotOk = 15
    EthercatCommError = 16
    ShuttleDriveError = 17
    ManuelAlarm = 18
    FrontLimit = 19
    BackLimit = 20
    ShuttleBoxSupplyFuse = 21
    Motor1BrakeFuse = 22
    Motor2BrakeFuse = 23
    InvertorCircuitBreaker = 24
    UPSFuse = 25
    GeneralAlarm = 26
    SafetyUpdateError = 27
    ModeOutofRange = 28
    EMGNotOK = 29
    ShuttleByPassKeyActive = 30  # Anahtar 1 iken false 0 iken True. Calismasi icin 0 olacak.
    CarFrontSwtich = 31
    CarBackSwtich = 32

    gaServiceDoorOpened = 48
    gaEMGPressed = 49
    gaEMGNotOK = 50
    gaNoCommonConfiguration = 51
    gaPLCSafetyUpdateError = 52
```

### TTurntableAlarm
```python title="PLC Variable"
class TTurntableAlarm(IntEnum):
    TurntableNotConfigured = 1
    TTEthercatCommError = 2
    TTInverterSafetyNotOK = 3
    TTDriveIsNotReadyWhenRunningTheTT = 4
    LockOpenTimeOut = 5
    LockCloseTimeOut = 6
    TTDriveError = 7
    NoServerConnection = 8
    ManuelAlarm = 9
    TTIsOutOfRangeWhenRunning = 10
    GeneralAlarm = 11
    ModeOutofRange = 12
    RelatedCarrierNotUpdated = 13
    RoomNotUpdated = 14
    TopConveyorNotUpdated = 15
    SafetyUpdateError = 16
    RelatedCarriersAreNotSafeToRunTheLift = 17
    LockIsNotOpened_WhenTTRunning = 18
    BrakeThermic = 19
    InverterCircuitBraker = 20
    LockThermic = 22
    RoomIsNotAuto = 23
    RoomNotSafeToMove = 24
    TopConveyorNotInAuto = 25
    TopConveyorNotIdleOrWaiting = 26
    PalletNotInLimits = 27
    CarWeightLimitExceeded = 28
    FacilityNotSafe = 29
    ShelvesNotSafe = 30
    RelatedCarriersNotSafe = 31
    TTPartsNotOk = 32
    gaServiceDoorOpened = 47
    gaEMGPressed = 48
    gaEMGNotOK = 49
    gaNoCommonConfiguration = 50
    gaMotorContactorError = 51
    gaPLCSafetyUpdateError = 52
```

### TShelfGroupAlarm
```python title="PLC Variable"
class TShelfGroupAlarm(IntEnum):
    ContactorOpenButItShouldBeClosed = 1
    LockIsOpenButItShouldBeClosed = 2
    ShelvesNotConfigured = 3
    ShelfInverterSafetyNotOK = 4
    EthercatCommError = 5
    ShelfDriveError = 6
    ManuelAlarm = 7
    GeneralAlarm = 8
    TimeOut = 9
    ConveyorError = 10
    HeightSensorsNotOk = 11
    SafetyUpdateError = 12
    ConveyorNotUpdated = 13
    InverterCircuitBraker = 14
    ShelfBrakeThermic = 15
    OverHeight = 16

    gaServiceDoorOpened = 47
    gaEMGPressed = 48
    gaEMGNotOK = 49
    gaNoCommonConfiguration = 50
    gaMotorContactorError = 51
    gaPLCSafetyUpdateError = 52
```

## Component Status

### TRoomStatus
```python title="PLC Variable"
class TRoomStatus(IntEnum):
    Unknown = 0
    OutOfService = 1
    Idle = 4
    WaitForEntry = 5
    WaitForExit = 6
    WaitForPallet = 7
    WaitForCar = 8
    Entry = 9
    Exited = 10
    CarDelivered = 11
```

### TConveyorStatus
```python title="PLC Variable"
class TConveyorStatus(IntEnum):
    Unknown = 0
    OutOfService = 1
    Idle = 2
    Taking = 3
    Giving = 4
    Waiting = 5
    GiveRequest = 6
    Centering = 7
```

### TCarrierStatus    
```python title="PLC Variable"
class TCarrierStatus(IntEnum):    
    Unknown = 0
    OutOfService = 1
    Idle = 2
    Running = 3
    Waiting = 4
```

### TShelfGroupStatus
```python title="PLC Variable"
class TShelfGroupStatus(IntEnum):
    Unknown = 0
    OutOfService = 1
    Idle = 2
    Taking = 3
    Giving = 4
    Waiting = 5
```

## Component Not Working

### TConveyorNotWorking
```python title="PLC Variable"
class TConveyorNotWorking(IntEnum):
    ConveyorWaitingStatus = 1
    NoNewJob = 2
    ConveyorDriveNotActive = 3
    ShelfDriveNotActive = 4
    CanNotTake = 5
    ShelfIsFull = 6
    ShelfIsNotEnabled = 7
    ShefIsNotActive = 8
    ShelfIsRunning = 9
    ShelfNotAuto = 10
    ShelfStatusNotIdle = 11
    WedgeSensorNotThere = 12
    PalletNotInLimits = 13
    CanNotGive = 14
    ShelfHasNoPallet = 15
    NotFullAndNoAttachmenet = 16
    FullButWedgeSensor = 17
    WaitForActiveShelfCanTake = 18
    ManuelStop = 19
    ThereIsError = 20
    StartConditionNotOk = 21
    ConveyorOutOfService = 22
```

### TLiftNotWorking
```python title="PLC Variable"
class TLiftNotWorking(IntEnum):
    RoomFlapConditionNotOk = 1
    RoomLockConditionNotOk = 2
    LiftSitInTheRoom = 3
    ShelfLocksAreOpen = 4
    WaitingForFlapCondition = 5
    WaitingForLockCondition = 6
    RoomNotAuto = 19
    RoomNotUpdated = 20
    RoomNotFree = 21
    ServiceDoorOpened = 22
    EMGPressed = 23
    EMGNotOK = 24
    NoCommonConfiguration = 25
    MotorContactorError = 26
    PLCSafetyUpdateError = 27
    ManuallyStopped = 28
    CarrierAlreadyRunning = 29
    CarrierInWaitingStatus = 30
    ThereIsError = 31
    CantMoveBelowMinPos = 32
    CantMoveAboveMaxPos = 33
    NoNewJob = 34
    CarrierIsAtTarget = 35
    TargetLTMinPos = 36
    TargetGTMaxPos = 37
    PartsNotSafe = 38
    TopConveyorNotSafe = 39
    RoomNotSafe = 40
    ShelvesNotSafe = 41
    FacilityNotSafe = 42
    RelatedCarriersNotSafe = 43
    TopConveyorCarHeavy = 44
    TopConveyorPalletOutOfLimits = 45
    TopConveyorNotIdleOrWaiting = 66
    TopConveyorNotAuto = 47
    TopConveyorNotUpdated = 48
    RoomDriverDoorNotLocked = 49
    RoomCarDoor2NotClosed = 50
    RoomCarDoor1NotClosed = 51
    RoomStatusNotOk = 52
```

### TShuttleNotWorking
```python title="PLC Variable"
class TShuttleNotWorking(IntEnum):
    ShelfLocksAreOpen = 1
    RoomNotAuto = 19
    RoomNotUpdated = 20
    RoomNotFree = 21
    ServiceDoorOpened = 22
    EMGPressed = 23
    EMGNotOK = 24
    NoCommonConfiguration = 25
    MotorContactorError = 26
    PLCSafetyUpdateError = 27
    ManuallyStopped = 28
    CarrierAlreadyRunning = 29
    CarrierInWaitingStatus = 30
    ThereIsError = 31
    CantMoveBelowMinPos = 32
    CantMoveAboveMaxPos = 33
    NoNewJob = 34
    CarrierIsAtTarget = 35
    TargetLTMinPos = 36
    TargetGTMaxPos = 37
    PartsNotSafe = 38
    TopConveyorNotSafe = 39
    RoomNotSafe = 40
    ShelvesNotSafe = 41
    FacilityNotSafe = 42
    RelatedCarriersNotSafe = 43
    TopConveyorCarHeavy = 44
    TopConveyorPalletOutOfLimits = 45
    TopConveyorNotIdleOrWaiting = 66
    TopConveyorNotAuto = 47
    TopConveyorNotUpdated = 48
    RoomDriverDoorNotLocked = 49
    RoomCarDoor2NotClosed = 50
    RoomCarDoor1NotClosed = 51
    RoomStatusNotOk = 52
```

### TTTNotWorking
```python title="PLC Variable"
class TTTNotWorking(IntEnum):
    WaitingForLockOpening = 1
    RoomNotAuto = 19
    RoomNotUpdated = 20
    RoomNotFree = 21
    ServiceDoorOpened = 22
    EMGPressed = 23
    EMGNotOK = 24
    NoCommonConfiguration = 25
    MotorContactorError = 26
    PLCSafetyUpdateError = 27
    ManuallyStopped = 28
    CarrierAlreadyRunning = 29
    CarrierInWaitingStatus = 30
    ThereIsError = 31
    CantMoveBelowMinPos = 32
    CantMoveAboveMaxPos = 33
    NoNewJob = 34
    CarrierIsAtTarget = 35
    TargetLTMinPos = 36
    TargetGTMaxPos = 37
    PartsNotSafe = 38
    TopConveyorNotSafe = 39
    RoomNotSafe = 40
    ShelvesNotSafe = 41
    FacilityNotSafe = 42
    RelatedCarriersNotSafe = 43
    TopConveyorCarHeavy = 44
    TopConveyorPalletOutOfLimits = 45
    TopConveyorNotIdleOrWaiting = 46
    TopConveyorNotAuto = 47
    TopConveyorNotUpdated = 48
    RoomDriverDoorNotLocked = 49
    RoomCarDoor2NotClosed = 50
    RoomCarDoor1NotClosed = 51
    RoomStatusNotOk = 52
```

### TShelfNotWorking
```python title="PLC Variable"
class TShelfNotWorking(IntEnum):
    ThereIsError = 1
    NoActiveShelf = 2
    WaitingForConveyor = 3
    StopAtWedge = 4
    ManuelStop = 5
```

## Component Safe To Move 

### TRoomSafeToMove
```python title="PLC Variable"
class TRoomSafeToMove(IntEnum):
    StatusNotConvenient = 1
    CarDoor1NotClosed = 2
    CarDoor2NotClosed = 3
    DriverDoorNotLocked = 4
```

### TCarrFBRoomSafe
```python title="PLC Variable"
class TCarrFBRoomSafe(IntEnum):
    RoomNotUpdated = 1
    RoomModeNotAuto = 2
    RoomNotSafeToMove = 3
```

### TCarrFBTopConveyorSafe
```python title="PLC Variable"
class TCarrFBTopConveyorSafe(IntEnum):
    ConveyorNotUpdated = 1
    ConveyorModeNotAuto = 2
    ConveyorStatusNotIdleOrWaiting = 3
    ConveyorPalletNotInLimits = 4
    CarIsHeavy = 5
```

### TCarrFBFacilitySafe
```python title="PLC Variable"
class TCarrFBFacilitySafe(IntEnum):
    ServiceDoorOpened = 58
    EMGPressed = 59
    EMGNotOK = 60
    NoCommonConfiguration = 61
    MotorContactorError = 62
    PLCSafetyUpdateError = 63
```

## Conveyor Conditions
### TConveyorStartCondition
```python title="PLC Variable"
class TConveyorStartCondition(IntEnum):
    LiftNotUpdated = 1
    LiftNotIdle = 2
    TurntableNotUpdated = 3
    TurntableNotIdle = 4
    ShuttleNotUpdated = 5
    ShuttleNotIdle = 6
    ShelfGroupNotUpdated = 7
    ShelfGroupNotIdle = 8
    RoomNotUpded = 9
    RoomNotSafeToMove = 10
    RoomStatusNotConvenient = 11
    RoomCarDoor1NotClosed = 12
    RoomCarDoor2NotClosed = 13
    RoomDriverDoorNotLocked = 14
    FrontLockNotOpened = 15
    RearLockNotOpened = 16
```

### TConveyorRunningCondition
```python title="PLC Variable"
class TConveyorRunningCondition(IntEnum):
    LiftNotUpdated = 1
    LiftNotWaiting = 2
    TurntableNotUpdated = 3
    TurntableNotWaiting = 4
    ShuttleNotUpdated = 5
    ShuttleNotWaiting = 6
    ShelfGroupNotUpdated = 7
    ShelfGroupOutOfService = 8
    RoomNotUpded = 9
    RoomNotSafeToMove = 10
    RoomStatusNotConvenient = 11
    RoomCarDoor1NotClosed = 12
    RoomCarDoor2NotClosed = 13
    RoomDriverDoorNotLocked = 14
    FrontLockNotOpened = 15
    RearLockNotOpened = 16
```

## Manuel Controls
### TRoomManuelControl
```python title="PLC Variable"
class TRoomManuelControl(IntEnum):
    NoCommand = 0
    OpenCarDoor1 = 1
    CloseCarDoor1 = 2
    OpenCarDoor2 = 3
    CloseCarDoor2 = 4
    OpenDriverDoor = 5
    LockDriverDoor = 7
    OpenWicket = 8
    CloseWicket = 9
    LeftFlapUp = 10
    LeftFlapDown = 11
    RightFlapUp = 12
    RightFlapDown = 13
    FlapsUp = 14
    FlapsDown = 15
    RightFrontPalletLockOpen = 16
    RightFrontPalletLockClose = 17
    RightBackPalletLockOpen = 18
    RightBackPalletLockClose = 19
    LeftFrontPalletLockOpen = 20
    LeftFrontPalletLockClose = 21
    LeftBackPalletLockOpen = 22
    LeftBackPalletLockClose = 23
    PalletLocksOpen = 24
    PalletLocksClose = 25
```

### TConveyorManuelControl
```python title="PLC Variable"
class TConveyorManuelControl(IntEnum):
    NoCommand = 0
    Stop = 1
    MoveLeft = 2
    MoveRight = 3
    OpenFrontLock = 4
    CloseFrontLock = 5
    OpenRearLock = 6
    CloseRearLock = 7
    OpenLocks = 8
    CloseLocks = 9
    OpenBrake = 10
    CloseBrake = 11
    CenterPallet = 12
```

### TLiftManuelControl
```python
class TLiftManuelControl(IntEnum):
    NoCommand = 0
    Stop = 1
    MoveUp = 2
    MoveDown = 3
    GoToPos = 4
    ServiceMotorUp = 5
    ServiceMotorDown = 6
```

### TShuttleManuelControl
```python title="PLC Variable"
class TShuttleManuelControl(IntEnum):
    NoCommand = 0
    Stop = 1
    MoveForward = 2
    MoveBackward = 3
    OpenBrake = 4
    CloseBrake = 5
```

### TTTManuelControl
```python title="PLC Variable"
class TTTManuelControl(IntEnum):
    NoCommand = 0
    Stop = 1
    TurnLeft = 2
    TurnRight = 3
    OpenLock = 4
    CloseLock = 5
    OpenBrake = 6
    CloseBrake = 7
    GoToBase = 8
    GoToDoor1 = 9
    GoToDoor1Op = 10
    GoToDoor2 = 11
    GoToDoor2Op = 12
```

### TShelfManuelControl
```python title="PLC Variable"
class TShelfManuelControl(IntEnum):
    NoCommand = 0
    Stop = 1
    Giving = 2
    Taking = 3
    OpenBrake = 4
    CloseBrake = 5
```

## Others
### TCarExistsControl
```python
class TCarExistsControl(IntEnum):
    ByLoadCell = 1
    BySensor = 2
    Both = 3
```

### TCarrierTargetType
```python
class TCarrierTargetType(IntEnum):
    Unknown = 0
    Shelf = 1
    Room = 2
    Door = 3
    Turning = 4
    FreePositioning = 5
    Conveyor = 6
```

### TCarrierType
```python
class TCarrierType(Enum):
    Lift = 1
    Shuttle = 2
    Turntable = 3
```

### TCHCat
```python
class TCHCat(IntEnum):
    EmptyPallet = 0
    Sedan = 1
    SUV = 2
```

### TConfirmMethod
```python
class TConfirmMethod(IntEnum):
    ByButton = 1
    ByCard = 2
```

### TConfigStat
```python
class TConfigStat(IntEnum):
    NoConfiguration = 0
    Configuring = 1
    Configured = 2
```

### TConveyorTargetType
```python
class TConveyorTargetType(IntEnum):
    Unknown = 0
    Shelf = 1
    Conveyor = 2
```

### TConveyorType
```python
class TConveyorType(IntEnum):
    Type1 = 1
```

### TDriveCommand
```python
class TDriveCommand(IntEnum):
    Nonee = 0
    Run = 1
    Stop = 2
    QStop = 3
    Activate = 4
```

### TJobStatus
```python
class TJobStatus(IntEnum):
    Unknown = 0
    Idle = 1
    Working = 2
    Completed = 3
    Cancelled = 4
```

### TLogType
```python
class TLogType(IntEnum):
    CarLog = 0
    CarrierLog = 1
    ShelfLog = 2
    ModeLog = 3
    AlarmLog = 4
    PalletLog = 5
```

### TOpenCloseState
```python
class TOpenCloseState(IntEnum):
    Unknown = 0
    Closed = 1
    Opening = 2
    Opened = 3
    Closing = 4
    InTheMiddle = 5
    Error = 6
```

### TPartMode
```python
class TPartMode(IntEnum):
    Unknown = 0
    Auto = 1
    Service = 2
    Error = 3
    Commissioning = 4
```

### TPartType
```python
class TPartType(IntEnum):
    Carrier = 1
    Shelf = 2
    Room = 3
    Conveyor = 4
```

### TPositioningType
```python
class TPositioningType(IntEnum):
    AbsolutePos = 1
    SensorPos = 2
```

### TProjectName
```python
class TProjectName(IntEnum):
    NotDefined = 0
    Trabzon = 1
    Dibaji = 2
    IzmirAdliye = 3
    TestSystem = 4
    TBank = 5
    Subasi = 6
```

### TRequestType
```python
class TRequestType(IntEnum):
    NoRequest = 0
    Exit = 1
    Bring = 2
```

### TRetrievalStatus
```python
class TRetrievalStatus(IntEnum):
    NoAction = 0
    Waiting = 1
    Preparing = 2
    Bringing = 3
    Ready = 4
    Halted = 5
```

### TRoomStep
```python
class TRoomStep(IntEnum):
    NoStep = 0
    WaitingCar = 1
    Approaching = 2
    CarEntering = 3
    Positioned = 4
    DriverLeaving = 5
    ReadyToConfirm = 6
    Confirmed = 7
    ReadyToMoveCar = 8
    CarIsReady = 11
    DoorsOpened = 12
    DriverEntering = 13
    CarLeaving = 14
    CarExited = 15
```

### TRoomType
```python
class TRoomType(IntEnum):
    Trabzon = 1
    Dibaji = 2
    TBank = 3
    IzmirAdliye = 4
```

### TRunStep
```python
class TRunStep(IntEnum):
    NotRunning = 0
    Init = 1
    Started = 2
    Running = 3
    Finished = 4
```

### TShelfDriveParam
```python
class TShelfDriveParam(IntEnum):
    StdTake = 1
    StdGive = 2
    LastPalletTake = 3
    LastPalletGive = 4
    TakeToBack = 5
    GiveFromBack = 6
    MoveToFront = 7
    MoveToBack = 8
```

### TShelfType
```python
class TShelfType(IntEnum):
    NotDefined = 0
    Standard = 1
    NoFirstPallet = 2
    Conveyor = 3
    Transfer = 4
```

### TShelvesMetrics
```python
class TShelvesMetrics(IntEnum):
    Number = 1
    Width = 2
    Height = 3
    Depth = 4
    ShelfWidth = 5
    ShelfHeight = 6
    ShelfDepth = 7
```

### TShelfStep
```python
class TShelfStep(IntEnum):
    Unknown = 0
    NotReady = 1
    ReadyToGetPallet = 2
    PalletOnShelf = 3
```

### TShuttleDriveParam
```python
class TShuttleDriveParam(IntEnum):
    Move = 1
```

### TShuttleStep
```python
class TShuttleStep(IntEnum):
    Unknown = 0
    Stopped = 1
    Running = 2
```

### TShuttleType
```python
class TShuttleType(IntEnum):
    NotDefined = 0
    Standard = 1
    Long = 2
```

### TStopReason
```python
class TStopReason(IntEnum):
    There_is_pallet_on_conveyor_at_PLC_but_not_in_the_System = 1
    There_is_no_pallet_on_conveyor_at_PLC_but_in_the_System = 2
    No_Shelf_found_to_put_Pallet = 3
    No_Shelf_found_to_get_Pallet = 4
```

### TTargetType
```python
class TTargetType(IntEnum):
    Unknown = 0
    Shelf = 1
    Room = 2
    Door = 3
    Turning = 4
    FreePositioning = 5
    Conveyor = 6
```

### TTaskType
```python
class TTaskType(IntEnum):
    Idle = 0
    TakePallet = 1
    BringPallet = 2
    BringExitCar = 3
```

### TWorkStatus
Conveyorun `WorkList` listesindeki `TWork` nesnesinin Status tipi: 
```python
class TWorkStatus(IntEnum):
    Waiting = 1
    GoingToSource = 2
    Taking = 3
    GoingToTarget = 4
    Putting = 5
    Completed = 6
```

### TWorkRelType
```python
class TWorkRelType(IntEnum):
    NoRel = 0
    TakeAfterPut = 1
```

### TYon
```python
class TYon(IntEnum):
    Left = 1
    Right = 2
```

# NOT IN USE
### TEPCounts(Enum):
```python
class TEPCounts(Enum):
    SelfShelves_ExclBuffers = 1
    OtherConveyors_ExclBuffers = 2
    OtherConveyors_InclBuffers = 3
    SelfShelves_InclBuffers = 4
```

### TShelfCanTake
```python
class TShelfCanTake(IntEnum):
    CapacityFull = 1
    ShelfNotEnabled = 2
    ShelfNotActive = 3
    ShelfDriveRunning = 4
    ShelfNotAuto = 5
    ShelfNotIdle = 6
    NoWedgeSensor = 7
```

### TShelfCanGive
```python
class TShelfCanGive(IntEnum):
    CapacityFull = 1
    ShelfNotEnabled = 2
    ShelfNotActive = 3
    ShelfDriveRunning = 4
    ShelfNotAuto = 5
    ShelfNotIdle = 6
    NotFullButNoWedgeSensor = 7
    FullButWedgeSensor = 7
```

### TRoomFree
```python
class TRoomFree(IntEnum):
    DriveDoorNotClosed = 1
    CHCat1Sensor = 2
    CHCat2Sensor = 3
    CH60cmSensor = 4
    FrontScanner = 5
    BackScanner = 6
    LeftScanner = 7
    RightScanner = 8
    RFScanner = 9
    LBScanner = 10
    AllRoomSanner = 11
    DynCHCat1Sensor1 = 12
    DynCHCat1Sensor2 = 13
    DynCHCat2Sensor1 = 14
    DynCHCat2Sensor2 = 15
    CarExists = 16
    PalletNotInTheRoom = 17
```

### TLightStatus
```python
class TLightStatus(IntEnum):
    Red = 1
    Green = 2
    Off = 3
    BlinkGreen = 4
    BlinkRed = 5
```
### TCPCommands
```python
class TCPCommands(IntEnum):
    UserConnected = 1
    ExitCar = 2
    BringCar = 3
    DeleteCar = 4
    ChangeRoomCanEnter = 5
    ChangeRoomCanExit = 6
    ChangeName = 7
    Reset = 8
    ChangeMode = 9
    ConfigPLC = 10
    ShelfPutPallet = 11
    ChangeShelfPalletCount = 12
    CancelJob = 13
    GoToTarget = 14
    GoToPos = 15
    UpdateProp = 16
    UpdateEENumbers = 17
    UpdateExitList = 18
```

### TFacilityCommand
```python
class TFacilityCommand(IntEnum):
    SetAMCH = 1
    OpenBarrier = 2
```

### TShelfFilter
```python
class TShelfFilter(IntEnum):
    All = 1
    HasEmptyPallet = 2
    HasEmptySpace = 3
    Full = 4
```