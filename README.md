# TI-BASIC-Pong-Implementation
A version of Pong that can be run on a TI-84 graphing calculator.  
For best experience, set the window to around x: 0-40 and y: 0-20. 
The up and down arrow keys are used to direct the (green) player controlled stick. The red stick is automatically operated.
The ball gets slightly faster as the game progresses. 
The first side to five points wins.
 
Because the code is in TI-BASIC, it needs special tools to be viewed in a form that can be read directly as text. Because of that, the code is here to be easily viewed:
```
DispGraph
0→[H](4,1)
0→[H](4,2)
While [H](4,1)<5 and [H](4,2)<5
DispGraph
10→[H](1,1)
10→[H](1,2)
20→[H](2,1)
10→[H](2,2)
­5→[H](3,1)
2→[H](3,2)
0→F
While not(F)
ClrDraw
For(I,­.5,.5,0.5)
For(J,­(.5-abs(I)),.5-abs(I),0.5)
Pt-On([H](2,1)+I,[H](2,2)+J)
End
End
Line(1,[H](1,1)-1,1,[H](1,1)+1,GREEN)
Line(39,[H](1,2)+1,39,[H](1,2)-1,RED)
If [H](2,1)≤0 or [H](2,1)≥40
Then
If abs([H](2,2)-[H](1,1))>3 and [H](2,1)<10 or abs([H](2,2)-[H](1,2))>3 and [H](2,1)>10
Then
1→F
Else
If [H](2,1)<10
Then
[H](3,2)+3.5*abs([H](3,2))*(((abs([H](1,1)-[H](2,2)))/7)^3)/[H](3,2)→[H](3,2)
Else
[H](3,2)+3.5*abs([H](3,2))*(((abs([H](1,2)-[H](2,2))/7)^3)/[H](3,2)→[H](3,2)
End
­[H](3,1)→[H](3,1)
End
End
If [H](2,2)<0 or [H](2,2)>20
­[H](3,2)→[H](3,2)
[H](2,1)+[H](3,1)→[H](2,1)
[H](2,2)+[H](3,2)→[H](2,2)
getKey→K
If K=25
[H](1,1)+3→[H](1,1)
If K=34
[H](1,1)-3→[H](1,1)
If [H](2,2)<[H](1,2)
[H](1,2)-1.9→[H](1,2)
If [H](2,2)≥[H](1,2)
[H](1,2)+1.9→[H](1,2)
End
If [H](2,1)>10
[H](4,1)+1→[H](4,1)
If [H](2,1)<10
[H](4,2)+1→[H](4,2)
ClrHome
Output(1,1,"HUMAN: ")
Output(1,8,[H](4,1)
Output(2,1,"COMPUTER: ")
Output(2,11,[H](4,2)
Wait 2.5
End

```
