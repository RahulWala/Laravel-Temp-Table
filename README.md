# Laravel-Temp-Table
Create Temp table in laravel

## How to create Temp Table in Laravel using Query Builder

Add **$table->temporary();** in migration up() function

Code for Temp Table fetch and insert

  ### Add Column

  $add_column = '(';
  for ($i = 0; $i <= ($get_no_of_seats['no_of_seats']); $i++) {
      $add_column .= "hello" . $i . " VARCHAR(5) ,";
  }
  $add_column = rtrim($add_column, ", ");

  ### Create query
  $tempTableData = DB::raw("CREATE TEMPORARY TABLE table_name " . $add_column . ")");
  $createTempTable = DB::unprepared($tempTableData);

  for ($i = 0; $i <= 5; $i++) {
      $data['hello' . $i] = '123';
  }
  $insertData = DB::table('table_name')->insert($data);

  $getTempTableData = DB::select("SELECT * FROM table_name");
  return $getTempTableData;
