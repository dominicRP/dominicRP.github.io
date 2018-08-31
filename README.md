<!DOCTYPE html>
<html lang="pt">
    <head>
        <meta charset="utf-8"/>
        <title>Currículo</title>
        <style>
        // Config: fonts
$font-mono: "Cutive Mono", monospace;
// Config: Ease
$ease-cb: cubic-bezier(.19,1,.22,1);


@mixin nth-trans-delay($delay_items: 7, $delay_time: 0.2s){
@for $i from 1 through $delay_items {
  &:nth-child(#{$i}) {   
   transition-delay: $delay_time * $i; 
  }
 }
}

@mixin nth-ani-delay($delay_items: 7, $delay_time: 0.2s){
@for $i from 1 through $delay_items {
  &:nth-child(#{$i}) {   
   animation-delay: $delay_time * $i; 
  }
 }
}

@mixin bg-overlay($bg_hex: #111, $bg_opacity: 0.6, $top_layer: 'header') {
  &:after {
    z-index: 0;
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    background: rgba($bg_hex, $bg_opacity);
  }
  
  // Layer atop overlay
  & > #{$top_layer}{
    z-index: 2;
    position: relative;
  }
}
//Setups
*, *:before, *:after {
  box-sizing: border-box; 
}
// Body
body {
  margin: 0;
  width: 100%;
  font-family: $font-mono;
  line-height: 1.5;
  font-weight: 400;
  font-style: normal;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale; 
  text-rendering: optimizeLegibility;
}

.sep{
  border: 0;
  width: 3em;
  height: 1px;
  margin: 1em 0;
  background-color: rgba(255,255,255,0.4);
}
.mast{
  position: relative;
  display:flex;
  align-items: center;
  width: 100%;
  height: 100vh;
  color: #fff;
  background-color: #111;
  @include bg-overlay(#111, 0.9);  
  
  &__bg{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    margin: 0;
    padding: 0;
    background-size: cover;
    background-position: 50%;
  }
  
  &__header{
    padding: 5%;
  }
  &__title{
    font-family: $font-mono;
    font-size: 1em;
    font-weight: 400;
    letter-spacing: 0.3em;
    text-transform: uppercase;
  }
  // Letter animation
  &__title span{
    animation: letter-glow 0.7s 0s ease both;
    @include nth-ani-delay(25, 0.05s);
  }
  //Letter animation
  &__text{
    font-family: $font-mono;
    font-size: 1em;
    margin: 0 0 0.5em;
    line-height: 1.5;
    white-space: pre;
  }
  
  &__text span{
    animation: letter-glow 0.7s 0s ease both;
    @include nth-ani-delay(180, 0.05s);
  }
}


// Letter Glow
@keyframes letter-glow{
  0%   { opacity: 0; text-shadow: 0px 0px 1px rgba(255,255,255,0.1)}
  66%  { opacity: 1; text-shadow: 0px 0px 20px rgba(255,255,255,0.9) }
  77%   { opacity: 1;  }
  100% { opacity:0.7; text-shadow: 0px 0px 20px rgba(255,255,255,0.0)}
}
        </style>
    </head>
<body>

<h1>Currículo</h1>
<h2>Dominic Rocha de Paulo</h2>
<h4>Brasileira, 23 anos, Goiânia-GO<br/>
E-mail: dominic.rp.s2@gmail.com<br />
Estudante de Sistemas de Informação - Universidade Federal de Goiás(UFG)
</h4>
<p>This is a paragraph.</p>

</body>
</html> 
