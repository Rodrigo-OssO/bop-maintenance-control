# Database Schema Documentation

## Equipment
- **Table**: Equipment  
- **Columns**:  
  - `EquipmentID`: INT, Primary Key  
  - `EquipmentName`: VARCHAR(255), Not Null  
  - `Type`: VARCHAR(50)  
  - `Location`: VARCHAR(100)  
  - `Status`: VARCHAR(50)  
- **Constraints**:  
  - Primary Key (`EquipmentID`)  
- **Indexes**:  
  - `EquipmentName_index`

## MaintenanceRecord
- **Table**: MaintenanceRecord  
- **Columns**:  
  - `RecordID`: INT, Primary Key  
  - `EquipmentID`: INT, Foreign Key  
  - `MaintenanceDate`: DATETIME  
  - `Description`: TEXT  
- **Constraints**:  
  - Primary Key (`RecordID`)  
  - Foreign Key (`EquipmentID` references Equipment.EquipmentID)  
- **Indexes**:  
  - `MaintenanceDate_index`

## InspectionGroup
- **Table**: InspectionGroup  
- **Columns**:  
  - `GroupID`: INT, Primary Key  
  - `GroupName`: VARCHAR(255), Not Null  
  - `Description`: TEXT  
- **Constraints**:  
  - Primary Key (`GroupID`)  
- **Indexes**:  
  - `GroupName_index`

## RepairKit
- **Table**: RepairKit  
- **Columns**:  
  - `KitID`: INT, Primary Key  
  - `EquipmentID`: INT, Foreign Key  
  - `Description`: TEXT  
  - `Components`: TEXT  
- **Constraints**:  
  - Primary Key (`KitID`)  
  - Foreign Key (`EquipmentID` references Equipment.EquipmentID)  
- **Indexes**:  
  - `KitID_index`

## RepairKitUsage
- **Table**: RepairKitUsage  
- **Columns**:  
  - `UsageID`: INT, Primary Key  
  - `KitID`: INT, Foreign Key  
  - `EquipmentID`: INT, Foreign Key  
  - `UsageDate`: DATETIME  
- **Constraints**:  
  - Primary Key (`UsageID`)  
  - Foreign Key (`KitID` references RepairKit.KitID)  
  - Foreign Key (`EquipmentID` references Equipment.EquipmentID)  
- **Indexes**:  
  - `UsageDate_index`

## MaintenanceSchedule
- **Table**: MaintenanceSchedule  
- **Columns**:  
  - `ScheduleID`: INT, Primary Key  
  - `EquipmentID`: INT, Foreign Key  
  - `ScheduledDate`: DATETIME  
  - `Frequency`: VARCHAR(50)  
- **Constraints**:  
  - Primary Key (`ScheduleID`)  
  - Foreign Key (`EquipmentID` references Equipment.EquipmentID)  
- **Indexes**:  
  - `ScheduledDate_index`

## Certifications
- **Table**: Certifications  
- **Columns**:  
  - `CertificationID`: INT, Primary Key  
  - `EquipmentID`: INT, Foreign Key  
  - `CertificationDate`: DATETIME  
  - `ExpirationDate`: DATETIME  
- **Constraints**:  
  - Primary Key (`CertificationID`)  
  - Foreign Key (`EquipmentID` references Equipment.EquipmentID)  
- **Indexes**:  
  - `CertificationDate_index`