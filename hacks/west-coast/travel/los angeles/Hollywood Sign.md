---
layout: post
title: "Los Angeles"
description: "Roadtrip through LA and learn UI while you're there!"
permalink: /west-coast/analytics/losangeles/HollywoodS
parent: "Analytics/Admin"
team: "Cool Collaborators"
submodule: 1
author: "Cool Collaborators"
date: 2025-10-21
---


<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1"/>
<title>Hollywood Sign — Roadtrip</title>
<style>
/* ===== Truck intro (8s) ===== */
body{background:#009688;overflow:hidden;font-family:'Open Sans',sans-serif}
.loop-wrapper{margin:0 auto;position:relative;display:block;width:600px;height:250px;overflow:hidden;border-bottom:3px solid #fff;color:#fff}
.mountain{position:absolute;right:-900px;bottom:-20px;width:2px;height:2px;box-shadow:0 0 0 50px #4DB6AC,60px 50px 0 70px #4DB6AC,90px 90px 0 50px #4DB6AC,250px 250px 0 50px #4DB6AC,290px 320px 0 50px #4DB6AC,320px 400px 0 50px #4DB6AC;transform:rotate(130deg);animation:mtn 20s linear infinite}
.hill{position:absolute;right:-900px;bottom:-50px;width:400px;border-radius:50%;height:20px;box-shadow:0 0 0 50px #4DB6AC,-20px 0 0 20px #4DB6AC,-90px 0 0 50px #4DB6AC,250px 0 0 50px #4DB6AC,290px 0 0 50px #4DB6AC,620px 0 0 50px #4DB6AC;animation:hill 4s 2s linear infinite}
.tree,.tree:nth-child(2),.tree:nth-child(3){position:absolute;height:100px;width:35px;bottom:0;background:url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/130015/tree.svg) no-repeat}
.rock{margin-top:-17%;height:2%;width:2%;bottom:-2px;border-radius:20px;position:absolute;background:#ddd}
.truck,.wheels{transition:all ease;width:85px;margin-right:-60px;bottom:0px;right:50%;position:absolute;background:#eee}
.truck{background:url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/130015/truck.svg) no-repeat;background-size:contain;height:60px}
.truck:before{content:" ";position:absolute;width:25px;box-shadow:-30px 28px 0 1.5px #fff,-35px 18px 0 1.5px #fff}
.wheels{background:url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/130015/wheels.svg) no-repeat;height:15px;margin-bottom:0}
.tree{animation:tree 3s 0s linear infinite}
.tree:nth-child(2){animation:tree2 2s .15s linear infinite}
.tree:nth-child(3){animation:tree3 8s .05s linear infinite}
.rock{animation:rock 4s -.53s linear infinite}
.truck{animation:truck 4s .08s ease infinite}
.wheels{animation:truck 4s .001s ease infinite}
.truck:before{animation:wind 1.5s 0s ease infinite}
@keyframes tree{0%{transform:translate(1350px)}100%{transform:translate(-50px)}}
@keyframes tree2{0%{transform:translate(650px)}100%{transform:translate(-50px)}}
@keyframes tree3{0%{transform:translate(2750px)}100%{transform:translate(-50px)}}
@keyframes rock{0%{right:-200px}100%{right:2000px}}
@keyframes truck{0%{}6%{transform:translateY(0)}7%{transform:translateY(-6px)}9%{transform:translateY(0)}10%{transform:translateY(-1px)}11%{transform:translateY(0)}100%{}}
@keyframes wind{0%{}50%{transform:translateY(3px)}100%{}}
@keyframes mtn{100%{transform:translateX(-2000px) rotate(130deg)}}
@keyframes hill{100%{transform:translateX(-2000px)}}
.intro{position:fixed;inset:0;display:grid;place-items:center;background:#009688;z-index:10}
.intro p{color:#fff;font-weight:800;margin-top:18px;text-shadow:0 2px 12px rgba(0,0,0,.35)}
/* ===== Scene: Hollywood Sign ===== */
.hidden{display:none}
.scene{position:relative;min-height:100vh;background:linear-gradient(#8fd0ff 0%,#cfefff 60%,#eaf6ff 100%)}
.hill{box-shadow:none}
.hill-shape{position:absolute;bottom:0;width:60%;height:40%;background:radial-gradient(circle at 50% 100%,#6fb36a 0%,#518f57 70%);left:var(--x);border-radius:50% 50% 0 0;filter:brightness(.95)}
.sign{position:absolute;bottom:46%;left:50%;transform:translateX(-50%);display:flex;gap:8px;filter:drop-shadow(0 6px 10px rgba(0,0,0,.25))}
.sign .ltr{width:28px;height:68px;background:#fff;border:5px solid #eaeaea;display:grid;place-items:center;font-weight:800;font-size:22px;color:#333}
.caption{position:absolute;left:50%;transform:translateX(-50%);bottom:22px;color:#2b2b2b;font-weight:600;background:rgba(255,255,255,.75);padding:8px 14px;border-radius:10px}
</style>
</head>
<body>
<!-- Truck intro -->
<div class="intro" id="intro">
  <div class="loop-wrapper" role="img" aria-label="Driving through teal hills toward Hollywood">
    <div class="mountain"></div>
    <div class="hill"></div>
    <div class="tree"></div><div class="tree"></div><div class="tree"></div>
    <div class="rock"></div>
    <div class="truck"></div>
    <div class="wheels"></div>
  </div>
  <p>Cruising up to the Hollywood Hills…</p>
</div>

<!-- Scene -->
<main class="scene hidden" id="scene">
  <div class="hill-shape" style="--x:-10%"></div>
  <div class="hill-shape" style="--x:20%"></div>
  <div class="hill-shape" style="--x:55%"></div>
  <div class="sign" aria-label="HOLLYWOOD sign">
    <div class="ltr">H</div><div class="ltr">O</div><div class="ltr">L</div><div class="ltr">L</div>
    <div class="ltr">Y</div><div class="ltr">W</div><div class="ltr">O</div><div class="ltr">O</div><div class="ltr">D</div>
  </div>
  <div class="caption">⛰️ Hollywood Sign — Sunlit hills overlooking LA</div>
</main>

<script>
setTimeout(()=>{
  document.getElementById('intro').classList.add('hidden');
  document.getElementById('scene').classList.remove('hidden');
  // optional: change body bg to match scene
  document.body.style.background = 'linear-gradient(#8fd0ff,#eaf6ff)';
}, 8000);
</script>
</body>
</html>


<!DOCTYPE html>
<html>
<head>
    <title>Hollywood Sign Button Lesson</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #000;
            color: #fff;
            margin: 0;
            padding: 40px 20px;
            line-height: 1.6;
            font-size: 16px;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
        }

        h1, h2, h3 {
            color: #fff;
            font-size: 16px;
            font-weight: bold;
            margin: 20px 0 10px 0;
        }

        p {
            color: #fff;
            font-size: 16px;
            margin: 10px 0;
        }

        pre {
            background: #1a1a1a;
            padding: 15px;
            border-radius: 5px;
            overflow-x: auto;
            color: #fff;
            font-size: 14px;
        }

        code {
            color: #fff;
            font-size: 14px;
        }

        .example-section {
            margin: 40px 0;
            padding: 30px;
            background: #1a1a1a;
            border-radius: 10px;
        }

        .demo-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 400px;
            background: linear-gradient(to bottom, #87CEEB 0%, #87CEEB 60%, #d2b48c 60%, #8b7355 100%);
            border-radius: 10px;
            position: relative;
            margin-top: 20px;
        }

        .button-container {
            margin-bottom: 50px;
            z-index: 10;
        }

        button {
            background-color: #e74c3c;
            color: white;
            padding: 25px 50px;
            font-size: 24px;
            font-weight: bold;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            box-shadow: 0 6px 12px rgba(0,0,0,0.3);
            transition: all 0.3s ease;
            text-transform: uppercase;
        }

        button:hover {
            background-color: #c0392b;
            transform: translateY(-3px);
            box-shadow: 0 8px 16px rgba(0,0,0,0.4);
        }

        button:active {
            transform: translateY(0);
            box-shadow: 0 4px 8px rgba(0,0,0,0.3);
        }

        #signContainer {
            opacity: 0;
            transform: scale(0.5) translateY(50px);
            transition: all 1s ease;
            z-index: 10;
        }

        #signContainer.show {
            opacity: 1;
            transform: scale(1) translateY(0);
        }

        .hollywood-sign {
            display: flex;
            gap: 15px;
            perspective: 1000px;
        }

        .letter {
            font-size: 80px;
            font-weight: 900;
            color: white;
            text-shadow: 
                4px 4px 0 #2c3e50,
                -2px -2px 0 #34495e,
                2px -2px 0 #34495e,
                -2px 2px 0 #34495e,
                0 0 30px rgba(255,255,255,0.6),
                0 0 60px rgba(255,255,255,0.3);
            font-family: 'Arial Black', sans-serif;
            animation: letterPop 0.5s ease backwards;
        }

        .letter:nth-child(1) { animation-delay: 0.1s; }
        .letter:nth-child(2) { animation-delay: 0.2s; }
        .letter:nth-child(3) { animation-delay: 0.3s; }
        .letter:nth-child(4) { animation-delay: 0.4s; }
        .letter:nth-child(5) { animation-delay: 0.5s; }
        .letter:nth-child(6) { animation-delay: 0.6s; }
        .letter:nth-child(7) { animation-delay: 0.7s; }
        .letter:nth-child(8) { animation-delay: 0.8s; }
        .letter:nth-child(9) { animation-delay: 0.9s; }

        @keyframes letterPop {
            from {
                opacity: 0;
                transform: rotateY(90deg) scale(0.3);
            }
            to {
                opacity: 1;
                transform: rotateY(0deg) scale(1);
            }
        }

        .hillside {
            position: absolute;
            bottom: 50px;
            width: 100%;
            height: 200px;
            overflow: hidden;
            z-index: 1;
        }

        .hill {
            position: absolute;
            bottom: 0;
            background: #6b8e23;
            border-radius: 50% 50% 0 0;
        }

        .hill1 {
            left: 10%;
            width: 300px;
            height: 150px;
        }

        .hill2 {
            left: 35%;
            width: 350px;
            height: 180px;
        }

        .hill3 {
            right: 15%;
            width: 320px;
            height: 160px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Los Angeles</h1>
        <h2>Hollywood Sign Button Lesson</h2>

        <h3>Step 1: Set Up Your HTML File</h3>
        <p>First, create a new file and save it as button.html. Every HTML file needs this basic structure:</p>
        <pre><code>&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;head&gt;
    &lt;title&gt;My Button&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;

&lt;/body&gt;
&lt;/html&gt;</code></pre>

        <p>What this means:</p>
        <p>&lt;!DOCTYPE html&gt; tells the browser this is an HTML file</p>
        <p>&lt;html&gt; wraps everything</p>
        <p>&lt;head&gt; contains information about the page</p>
        <p>&lt;body&gt; is where your visible content goes</p>

        <h3>Step 2: Create Your First Button</h3>
        <p>Inside the &lt;body&gt; tags, add a button:</p>
        <pre><code>&lt;body&gt;
    &lt;button&gt;Click Me!&lt;/button&gt;
&lt;/body&gt;</code></pre>

        <h3>Step 3: Make the Button Do Something</h3>
        <p>Add an onclick attribute to make something happen when clicked:</p>
        <pre><code>&lt;button onclick="alert('Hello!')"&gt;Click Me!&lt;/button&gt;</code></pre>

        <div class="example-section">
            <h3>Here's an example button!</h3>
            <div class="demo-container">
                <div class="hillside">
                    <div class="hill hill1"></div>
                    <div class="hill hill2"></div>
                    <div class="hill hill3"></div>
                </div>

                <div class="button-container">
                    <button onclick="generateHollywoodSign()">Click for Hollywood Sign</button>
                </div>

                <div id="signContainer">
                    <div class="hollywood-sign">
                        <div class="letter">H</div>
                        <div class="letter">O</div>
                        <div class="letter">L</div>
                        <div class="letter">L</div>
                        <div class="letter">Y</div>
                        <div class="letter">W</div>
                        <div class="letter">O</div>
                        <div class="letter">O</div>
                        <div class="letter">D</div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        function generateHollywoodSign() {
            var signContainer = document.getElementById('signContainer');
            
            // Reset animation by removing and re-adding the class
            signContainer.classList.remove('show');
            
            // Small delay to allow reset
            setTimeout(function() {
                signContainer.classList.add('show');
            }, 50);
        }
    </script>
</body>
</html>