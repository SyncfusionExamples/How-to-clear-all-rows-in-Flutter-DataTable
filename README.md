# How to clear all rows in Flutter DataTable (SfDataGrid) ?

In this article, we will show you how to clear all rows in [Flutter DataTable](https://www.syncfusion.com/flutter-widgets/flutter-datagrid).

Initialize the [SfDataGrid](https://pub.dev/documentation/syncfusion_flutter_datagrid/latest/datagrid/SfDataGrid-class.html) widget with all necessary properties. The SfDataGrid relies on DataGridSource to retrieve row data. The number of rows and row selection depend on [DataGridSource.rows](https://pub.dev/documentation/syncfusion_flutter_datagrid/latest/datagrid/DataGridSource/rows.html). To remove all rows, set DataGridSource.rows to an empty list ([]). After clearing the rows, call [notifyListeners()](https://pub.dev/documentation/syncfusion_flutter_datagrid/latest/datagrid/DataGridSourceChangeNotifier/notifyListeners.html) to update the SfDataGrid and reflect the changes in the UI, ensuring smooth updates, especially during CRUD operations.

```dart
@override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text('Syncfusion Flutter DataGrid')),
      body: Column(
        children: [
          TextButton(
            onPressed: () {
              employeeDataSource._employeeData = [];
              employeeDataSource.notifyListeners();
            },
            child: Text('Clear rows'),
          ),
          Expanded(
            child: SfDataGrid(
              source: employeeDataSource,
              selectionMode: SelectionMode.multiple,
              columnWidthMode: ColumnWidthMode.fill,
              columns: <GridColumn>[
                GridColumn(
                  columnName: 'id',
                  label: Container(
                    padding: EdgeInsets.all(16.0),
                    alignment: Alignment.center,
                    child: Text('ID'),
                  ),
                ),
                GridColumn(
                  columnName: 'name',
                  label: Container(
                    padding: EdgeInsets.all(8.0),
                    alignment: Alignment.center,
                    child: Text('Name'),
                  ),
                ),
                GridColumn(
                  columnName: 'designation',
                  label: Container(
                    padding: EdgeInsets.all(8.0),
                    alignment: Alignment.center,
                    child: Text('Designation', overflow: TextOverflow.ellipsis),
                  ),
                ),
                GridColumn(
                  columnName: 'salary',
                  label: Container(
                    padding: EdgeInsets.all(8.0),
                    alignment: Alignment.center,
                    child: Text('Salary'),
                  ),
                ),
              ],
            ),
          ),
        ],
      ),
    );
  }
```

You can download this example on [GitHub](https://github.com/SyncfusionExamples/How-to-clear-all-rows-in-Flutter-DataTable).