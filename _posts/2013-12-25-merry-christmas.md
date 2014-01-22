---
layout: post
title: "Merry Christmas"
description: ""
category: 
tags: []
---
{% include JB/setup %}
<script type="text/javascript"
src="http://qzonestyle.gtimg.cn/qzone/openapi/qc_loader.js" charset="utf-8" data-callback="true"></script>
<div>
    <p>学习html5 canvas过程中, 在csdn看到了用canvas简单描绘了圣诞树，觉得挺有意思的， 就自己模仿其源码自己弄了一个，主要是巩固自己所学, 祝大家圣诞节快乐!!!</p>
    原著地址:<a>http://www.spjeff.com/2013/12/05/christmas-tree-html5-js-and-css3/</a>
</div>

<div>
    <canvas id="mycanvas" height="200" width="200"></canvas>
    <script type="text/javascript">
        function drawTree() {
            var canvas = document.getElementById("mycanvas");
            if (canvas.getContext){
                var ctx = canvas.getContext('2d');
                ctx.fillStyle = "green";
                ctx.fillRect(60, 50, 40, 90);
                ctx.fillRect(40, 100, 80, 70);

                a = 60;
                b = 10;
                for (var i=0; i<5; i++){
                drawLeaf(-20 + a - (i * 10), b + (i * 30), ctx, "left");
                drawLeaf(20 + a + (i * 10), b + (i * 30), ctx, "right");
                }

                ctx.fillStyle = "brown";
                ctx.fillRect(70, 150, 20, 50);
                drawStar(ctx, 80, 20, 20, 5, 0.5);
            }
            else {
                alert("you need Firefox 1.5+ to see this demo");
            }
        }

        function drawLeaf(x, y, ctx, style){
            ctx.beginPath();
            ctx.fillStyle = "green";
            if (style == "right"){
                ctx.moveTo(x, y);
                ctx.lineTo(x + 40, y + 40);
                ctx.lineTo(x, y + 40);
            } else {
                ctx.moveTo(x + 40, y);
                ctx.lineTo(x, y + 40);
                ctx.lineTo(x + 40, y + 40);
            }

            ctx.fill();
        }

        function drawStar(ctx, x, y, r, p, m) {
            ctx.fillStyle = "gold";
            ctx.beginPath();
            ctx.translate(x, y);
            ctx,moveTo(0, 0 - r);
            for (var i=0; i<p; i++){
                ctx.rotate(Math.PI/ p);
                ctx.lineTo(0, 0 - (r * m));
                ctx.rotate(Math.PI / p);
                ctx.lineTo(0, 0 - r);
            }
            ctx.fill();
            ctx.restore();
        }

    window.setTimeout(drawTree, 1000);
  </script>
</div>
<div>
    <p>以下是圣诞树源代码</p>
    <pre>
        &lt;script type="text/javascript"&gt;
            function drawTree() {
                var canvas = document.getElementById("mycanvas");
                if (canvas.getContext){
                    var ctx = canvas.getContext('2d');
                    ctx.fillStyle = "green";
                    ctx.fillRect(60, 50, 40, 90);
                    ctx.fillRect(40, 100, 80, 70);

                    a = 60;
                    b = 10;
                    for (var i=0; i<5; i++){
                    drawLeaf(-20 + a - (i * 10), b + (i * 30), ctx, "left");
                    drawLeaf(20 + a + (i * 10), b + (i * 30), ctx, "right");
                    }

                    ctx.fillStyle = "brown";
                    ctx.fillRect(70, 150, 20, 50);
                    drawStar(ctx, 80, 20, 20, 5, 0.5);
                }
                else {
                    alert("you need Firefox 1.5+ to see this demo");
                }
            }

            function drawLeaf(x, y, ctx, style){
                ctx.beginPath();
                ctx.fillStyle = "green";
                if (style == "right"){
                    ctx.moveTo(x, y);
                    ctx.lineTo(x + 40, y + 40);
                    ctx.lineTo(x, y + 40);
                } else {
                    ctx.moveTo(x + 40, y);
                    ctx.lineTo(x, y + 40);
                    ctx.lineTo(x + 40, y + 40);
                }

                ctx.fill();
            }

            function drawStar(ctx, x, y, r, p, m) {
                ctx.fillStyle = "gold";
                ctx.beginPath();
                ctx.translate(x, y);
                ctx,moveTo(0, 0 - r);
                for (var i=0; i<p; i++){
                    ctx.rotate(Math.PI/ p);
                    ctx.lineTo(0, 0 - (r * m));
                    ctx.rotate(Math.PI / p);
                    ctx.lineTo(0, 0 - r);
                }
                ctx.fill();
                ctx.restore();
            }
            window.setTimeout(drawTree, 1000);
        &lt;/script&gt;
    </pre>
</div>

