﻿<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1" />
	<title>自適應</title>
	<script src="vue2.4.0.min.js"></script>
	<link rel="stylesheet" href="index.css">
</head>
<body>
	<div id="app" class="container">
		<div v-for="(div,index) in divs" class="inner">
			<div v-for="left,index2 in div.inner">
				<div class="leftcircle">
					   <div class="circle">
					   				            <!--進度圓->
				            <!--左半边圆-->
				            <div class="circle_left">
				                <div class="clip_left">
				     			 </div>
				            </div>
				            <!--右半边圆-->
				            <div class="circle_right">
				                <div class="clip_right"></div>
				            </div>

				            <div class="mask">

				                <span class="value">{{left.value}}</span><span class="value" id="percent">%</span>
				                <span class="name">{{left.name}}</span>
				            </div>
				        </div>
				</div>
				<div class="rightmsg"><li  v-for="list in left.message" style="color:#60fcc0;"><span>{{list.msg}}</span></li>	</div>		
			</div>
		</div>
	</div>
	 <script src="jquery.min.js"></script>
        <script>
            $(function(){
            	$a=$('.mask .value1').text().replace("%","");

                if( $a <= 50 ){
                    $('.circle_right').css('transform','rotate('+($a*3.6)+'deg)');
                }else{
                    $('.circle_right').css({
                        'transform':'rotate(0deg)',
                        "background":"red"
                    });
                    $('.circle_left').css('transform','rotate('+(($a-50)*3.6)+'deg)');
                }
            })
        </script>
	<script>
		var app=new Vue({
			el:'#app',
			data:{
				"divs":[
					{	
						inner:
						[
							{
								value:20,
								name:"烟感",
								message:[
								{msg:"封包流量：132"},
								{msg:"URL1：https://mall.googal.com/mail/u/1/#inbox"},
								
								]
							},
							
						]
					},
					{	
						inner:
						[
							{
								value:70,
								name:"烟感",
								message:[
								{msg:"封包流量：132"},
								{msg:"URL1：https://mall.googal.com/mail/u/1/#inbox"},
								{msg:"URL2：https://mall.googal.com/mail/u/1/#inbox"},
								]
							},
							
						]
					},
					{	
						inner:
						[
							{
								value:50,
								name:"烟感",
								message:[
								{msg:"封包流量：132"},
								{msg:"URL1：https://mall.googal.com/mail/u/1/#inbox"},
								{msg:"URL2：https://mall.googal.com/mail/u/1/#inbox"},
								]
							},
							
						]
					},
					{	
						inner:
						[
							{
								value:40,
								name:"烟感",
								message:[
								{msg:"封包流量：132"},
								{msg:"URL1：https://mall.googal.com/mail/u/1/#inbox"},
								
								]
							},
							
						]
					}
				]
			}
		})
	</script>
</body>
</html>