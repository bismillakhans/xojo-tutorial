# xojo-tutorial
xojo learning tricks and tips learn on the duration of corona lockdown 


## connect mysql server 
    StockDB = New MySQLCommunityServer  

    StockDB.Host = "127.0.0.1"
    StockDB.UserName = "auggen"
    StockDB.Password = "password"
    StockDB.DatabaseName = "test"

    Try
      StockDB.Connect
      mIsConnected = True
      MessageBox("connected")
    Catch e As DatabaseException
      MessageBox( "Error connecting to MySQL: " + e.Message)
    End Try
### here StockDB is the MySQLCommunityServer property intialized on the xojo editor section


## Data Reading and excuting display on datalist

    DataList.RemoveAllRows

    Var sql As String
    sql = "SELECT * FROM Team;"

    Var data As RowSet
    Try
      data = mDB.SelectSQL(sql)
    Catch e As DatabaseException
      MessageBox("DB Error: " + e.Message)
      Return
    End Try

    If data <> Nil Then
      For Each row As DatabaseRow In data
        DataList.AddRow(row.ColumnAt(0).StringValue, row.ColumnAt(1).StringValue, _
        row.ColumnAt(2).StringValue, row.ColumnAt(3).StringValue)
      Next

      data.Close
    End If
