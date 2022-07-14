
> Sub a()
> 
> Worksheets("Sheet1").Activate
> 
> Set myCell = Application.InputBox( _prompt:="Select a cell", Type:=8)
> 
>    Debug.Print myCell
>    
>End Sub
