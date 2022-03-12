<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel ="stylesheet" href="http://maxcdn.bootstrapcdn.com/boots...">
    <title>Tic Tac Toe Game</title>
</head>
<style>
    #table{
        padding: 16px;
    }
td{
    height:130px;
    width: 130px;
    border: 3px solid white;
    
}
tr{
    text-align: center;
    text-decoration-color: white;
    font-size:350%;
    font-family: sans-serif;
    color: black;
}
.demo1
    {background-color: #6666ff;}

.demo2{background-color:#ccccff ;}
body{
    background-color: whitesmoke;
}
div{
    text-align: center;
    font-size:xx-large;
}
</style>
<body>
    <div  id="gameDiv" style="display: none;">
        <table border="1" class="table" align="center">
        <tr>
        <td id="1" onclick="setVal(1)" class="demo1"></td>
        <td id="2" onclick="setVal(2)" class="demo2"></td>
        <td id="3" onclick="setVal(3)" class="demo1"></td>
        </tr>


        <tr>
            <td id="4" onclick="setVal(4)" class="demo2"></td>
            <td id="5" onclick="setVal(5)" class="demo1"></td>
            <td id="6" onclick="setVal(6)" class="demo2"></td>
            </tr>

         <tr>
            <td id="7" onclick="setVal(7)" class="demo1"></td>
            <td id="8" onclick="setVal(8)" class="demo2"></td>
            <td id="9" onclick="setVal(9)" class="demo1"></td>
            </tr>
        
    </table>
    <input type="button" value="Restart" onclick="restart()">
    <input type="button" value="UNDO" onclick="Undo()">
    </div>
    <div id="info">
    User1 : <input type="text" id="user1" ><br>
    User2:<input type="text" id="user2"><br>
    <input type="button" value ="start game" onclick="start()">
</div>


   <script>
       var count=0,Values=[0,0,0,0,0,0,0,0,0];
       var lastIndex;
       var user1,user2;
       console.log(Values);
    function start()
    {
        user1=document.getElementById("user1").value;
        user2=document.getElementById("user2").value;
        document.getElementById("info").style.display="none";
        document.getElementById("gameDiv").style.display="block";

    }
       function setVal(index)
       {
          
            count++;
            if(count%2==1)
            {
                if(Values[index]==0)
                {
                    document.getElementById(index).innerHTML="X";
                    Values[index]="X";
                }
                else
                {
                    count--;
                }
                
            }
            else
            {
                if(Values[index]==0)
                {
                    document.getElementById(index).innerHTML="O";
                    Values[index]="O";
                }
                else
                {
                    count--;
                }
            }
            lastIndex=index;
            if(count>4)
            getWinner(count);
            console.log(Values);
       }

       function getWinner(val)
       {
           if((Values[0]==Values[1] && Values[1]==Values[2]) ||(Values[3]==Values[4] && Values[4]==Values[5]) ||(Values[6]==Values[7] && Values[7]==Values[8]))
           {
               if(val%2==0)
               alert(user2+"  Winner..");
               else
               alert(user1 +"  Winner..");

           }
           else if((Values[0]==Values[3] && Values[3]==Values[6]) ||(Values[1]==Values[4] && Values[4]==Values[7]) ||(Values[2]==Values[5] && Values[5]==Values[8]))
           {
            if(val%2==0)
               alert(user2+"  Winner..");
               else
               alert(user1 +"  Winner..");
           }
           else if((Values[0]==Values[4] && Values[4]==Values[8]) ||(Values[2]==Values[4] && Values[4]==Values[6]))
           {
            if(val%2==0)
               alert(user2+"  Winner..");
               else
               alert(user1 +"  Winner..");
           }
           else
           {
               if(count>8)
               {
                    alert("Please Restart the Game ...");
               }
           }
       }


       function restart()
       {
           location.reload();
       }
   </script>

</body>
</html>
