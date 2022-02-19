# Lasarus-Typhon-performance
Simple option to speed up programs created with Lasarus/Typhon.

There are many complaints about the speed of programs created with the Lazarus/Typhon IDE.
There is an option that cannot be set through the program menu, but which can increase performance: 
{$PIC OFF}
https://www.freepascal.org/docs-html/prog/progsu111.html#x119-1200001.3.28
Example:
```
//{$PIC OFF}
program testb_tpc;
var
  i: QWord;
  S: QWord;
begin
  S:=0;
  for i:=0 to 29999999 do
       S+=i;
  WriteLn(S);
end.
```
```
time ./testb_tpc 
449999985000000

real	0m0,091s
user	0m0,091s
sys	0m0,001s
```
```
{$PIC OFF}
program testb_tpc;
var
  i: QWord;
  S: QWord;
begin
  S:=0;
  for i:=0 to 29999999 do
       S+=i;
  WriteLn(S);
end.
```
```
time ./testb_tpc 
449999985000000

real	0m0,017s
user	0m0,017s
sys	0m0,001s
```
