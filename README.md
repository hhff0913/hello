<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .box{
            width: 1000px;
            height: 600px;
            position: relative;
            margin:0 auto;
            border: solid 5px purple;
        }
        .left{
            position: absolute;
            left: 0px;
            top: 50%;
            margin-top: -20px;
            display: inline-block;
            width: 40px;
            height: 40px;
            background: rgba(255,255,0,0.5);
            text-align: center;
            line-height: 40px;
            color: white;
            cursor:pointer
        }
        .right{
            position: absolute;
            right: 0px;
            top: 50%;
            margin-top: -20px;
            display: inline-block;
            width: 40px;
            height: 40px;
            background: rgba(255,255,0,0.5);
            text-align: center;
            line-height: 40px;
            color: white;
            cursor:pointer
        }
        .dj{
            position: absolute;
            left:50%;
            bottom: 20px;
            margin-left: -150px;
        }
        .dj li{
            float: left;
            background: white;
            width: 20px;
            height:20px;
            margin: 5px;
            border-radius: 50%;
            list-style: none;
        }
        .dj .bg{
            background: yellow;
        }
        img{
            width: 1000px;
            height: 600px;


        }

    </style>
</head>
<body>
<div class="box">
    <img src="0.jpg" alt="">
    <div class="left">&lt;</div><div class="right">&gt;</div>
    <ul class="dj">
        <li class="bg"></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
    </ul>
</div>
<script>
    var li=document.getElementsByTagName('li');
    var img=document.getElementsByTagName('img')[0];
    var left=document.getElementsByClassName('left')[0];
    var right=document.getElementsByClassName('right')[0];
    var k=0
    for(i=0;i<li.length;i++){
        li[i].onmouseover=function () {
            for (j=0;j<li.length;j++){
                li[j].className='';
                if(li[j]==this){
                    img.src=j+'.jpg';
                    this.className='bg'
                }
            }
        }
    }
    left.onclick=function () {
        k--;
        if(k<0){
            k=9
        }
        img.src=k+'.jpg'
        for(n=0;n<li.length;n++){
            if(n==k){
                li[n].className='bg'
            }
            else {
                li[n].className=''
            }
        }
    }
    right.onclick=function () {
        k++;
        if(k>9){
            k=0
        }
        img.src=k+'.jpg'
        for(n=0;n<li.length;n++){
            if(n==k){
                li[n].className='bg'
            }
            else {
                li[n].className=''
            }
        }
    }
</script>
</body>
</html>
