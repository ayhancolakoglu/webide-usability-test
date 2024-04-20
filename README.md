
# Usability-Test SAP  WEB IDE 

## Datenbank Tabellen 

### Tabelle "Employees"  Employees.hdbtable
```sql
COLUMN TABLE "Employees" (
    "EmployeeID" INTEGER,
    "Name" NVARCHAR(100),
    "DepartmentID" INTEGER,
    "Salary" INTEGER,
    primary key ("EmployeeID")
);
```


### Tabelle "Departments"  Deaprtments.hdbtabledata
```sql
COLUMN TABLE "Departments" (
    "DepartmentID" INTEGER,
    "DepartmentName" NVARCHAR(100),
    primary key ("DepartmentID")
);
```

# Datenimport-Konfigurationen

## Import für "Employees" Employees.hdbtabledata
```json
{
  "format_version": 1,
  "imports": [
    {
      "target_table": "Employees",
      "source_data": {
        "data_type": "CSV",
        "file_name": "Employees.csv",
        "has_header": true,
        "dialect": "HANA",
        "type_config": {
          "delimiter": ","
        }
      },
      "import_settings": {
        "import_columns": ["EmployeeID", "Name", "DepartmentID", "Salary"],
        "column_mappings": {
          "EmployeeID": 1,
          "Name": 2,
          "DepartmentID": 3,
          "Salary": 4
        }
      }
    }
  ]
}
```
 ## Import für "Department" Departments.hdbtabledata
```json
{
  "format_version": 1,
  "imports": [
    {
      "target_table": "Departments",
      "source_data": {
        "data_type": "CSV",
        "file_name": "Departments.csv",
        "has_header": true,
        "dialect": "HANA",
        "type_config": {
          "delimiter": ","
        }
      },
      "import_settings": {
        "import_columns": ["DepartmentID", "DepartmentName"],
        "column_mappings": {
          "DepartmentID": 1,
          "DepartmentName": 2
        }
      }
    }
  ]
}
```
## Load Dateien 

### Loads für "Employees"  Employees.csv
```plaintext
EmployeeID,Name,DepartmentID,Salary
1,John Doe,101,60000
2,Jane Smith,102,75000
3,Emily Jones,101,50000
4,Chris Brown,103,65000
```

### Loads für "Departments" Departments.csv
```plaintext
DepartmentID,DepartmentName
101,IT
102,Human Resources
103,Finance
```







