Sub ClearBioData()
Range("D20:G1048570").ClearContents
Call Dclear
End Sub

Sub Dinput()

Set AWB = Workbooks(ActiveWorkbook.name)
Set AWS = AWB.ActiveSheet

Dim xToMax, x, y, p, q, teri, yaki, coco, cola As Long
Dim k As Double
'Application.ScreenUpdating = False
q = 24
p = 13
teri = 20
yaki = 13
coco = 33
cola = 13
xToMax = Cells(13, 9)

For x = 24 To xToMax

If AWS.Cells(x, 6) * AWS.Cells(x + 1, 6) < 0 Then
' RP switch
    If q > 32 Then
    p = p + 1
    q = 24
    End If
' Vend input
' iend input
AWS.Cells(q, p) = AWS.Cells(x, 5)
AWS.Cells(q + 10, p) = AWS.Cells(x, 6) / 1000
q = q + 1

ElseIf AWS.Cells(x, 6) * AWS.Cells(x + 1, 6) = 0 And AWS.Cells(x, 6) + AWS.Cells(x + 1, 6) <> 0 Then
If Cells(x, 6) = 0 Then
AWS.Cells(teri, yaki) = AWS.Cells(x, 5)
AWS.Cells(teri + 3, yaki) = AWS.Cells(x, 7)
yaki = yaki + 1
'Debug.Print teri, yaki
' OCV input
' Charge input
Else
AWS.Cells(coco, cola) = AWS.Cells(x, 5)
'Debug.Print coco, cola, "E"
AWS.Cells(coco + 10, cola) = AWS.Cells(x, 6) / 1000
'Debug.Print coco, cola, "i"
cola = cola + 1
End If
' Vend_10 input
' iend_10 input
End If
Debug.Print p, q
Next x
'Application.ScreenUpdating = True
End Sub

Sub DSolver()

Dim i As Long, y As Long
Dim wb As Workbook, AWB As Workbook, ws As Worksheet, AWS As Worksheet

For i = 13 To 34
    If Cells(19, i) <> 0 Then
    SolverOk SetCell:=Cells(74, i), MaxMinVal:=2, ValueOf:=0, ByChange:=Range(Cells(4, i), Cells(6, i)), _
        Engine:=1, EngineDesc:="GRG Nonlinear"

    SolverSolve userfinish:=True
    Cells(7, i) = Cells(5, i) / Cells(10, 9)
    End If
    
Next i

End Sub

Sub Dclear()
Range("M24:AH43").ClearContents
Range("M20:AH20").ClearContents
Range("M23:AH23").ClearContents
Range("M4:AH7").ClearContents


End Sub

Sub MakeGraphEi()
Li = 18
Be = 36
f = 18
For i = 13 To 34
If Cells(9, i) <> 0 Then
For f = 18 To 75
Cells(Li, Be) = Cells(f, i)
Li = Li + 1
Next f
Be = Be + 1
Li = 18
End If

Next i
Debug.Print i, Be

End Sub

Sub RefreshGraph()
Range("AJ24:AL75").ClearContents
Call MakeGraphEi
End Sub
Sub ClearBioData()
Range("D20:G1048570").ClearContents
Call Dclear
End Sub




