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


