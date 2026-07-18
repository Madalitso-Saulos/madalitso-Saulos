<svg width="100%" height="300" viewBox="0 0 800 300" xmlns="http://www.w3.org/2000/svg">

<defs>

  <filter id="glow">
    <feGaussianBlur stdDeviation="3" result="blur"/>
    <feMerge>
      <feMergeNode in="blur"/>
      <feMergeNode in="SourceGraphic"/>
    </feMerge>
  </filter>

  <linearGradient id="lineGlow">
    <stop offset="0%" stop-color="#00ffff" stop-opacity="0"/>
    <stop offset="50%" stop-color="#00ffff"/>
    <stop offset="100%" stop-color="#00ffff" stop-opacity="0"/>
  </linearGradient>

</defs>


<!-- Background -->
<rect width="800" height="300" fill="#05080f"/>


<!-- Digital Grid -->
<g opacity="0.12" stroke="#00ffff">
<path d="M0 50H800 M0 100H800 M0 150H800 M0 200H800 M0 250H800"/>
<path d="M100 0V300 M200 0V300 M300 0V300 M400 0V300 M500 0V300 M600 0V300 M700 0V300"/>
</g>



<!-- Network Connections -->
<g stroke="#00ffff" stroke-width="1" opacity="0.6">

<path d="M120 150 L220 80 L350 140 L470 70 L650 150"/>
<path d="M220 80 L250 220 L350 140 L520 220 L650 150"/>
<path d="M350 140 L470 250"/>
<path d="M470 70 L520 220"/>

</g>



<!-- Network Nodes -->
<g fill="#00ffff" filter="url(#glow)">

<circle cx="120" cy="150" r="6">
<animate attributeName="r" values="6;10;6" dur="2s" repeatCount="indefinite"/>
</circle>

<circle cx="220" cy="80" r="6">
<animate attributeName="r" values="6;11;6" dur="2.5s" repeatCount="indefinite"/>
</circle>

<circle cx="350" cy="140" r="8">
<animate attributeName="r" values="8;13;8" dur="1.8s" repeatCount="indefinite"/>
</circle>

<circle cx="470" cy="70" r="6">
<animate attributeName="r" values="6;10;6" dur="2s" repeatCount="indefinite"/>
</circle>

<circle cx="650" cy="150" r="7">
<animate attributeName="r" values="7;12;7" dur="2s" repeatCount="indefinite"/>
</circle>

<circle cx="520" cy="220" r="6"/>

<circle cx="250" cy="220" r="6"/>

</g>



<!-- Moving Data Packets -->

<circle r="4" fill="#00ffff">
<animateMotion dur="4s" repeatCount="indefinite">
<mpath href="#route"/>
</animateMotion>
</circle>

<path id="route" d="M120 150 L220 80 L350 140 L470 70 L650 150"
fill="none"/>



<!-- Cybercafe Terminal Codes -->

<g fill="#00ffff" font-family="monospace">


<text x="35" y="35" font-size="16">
&lt; CYBERCAFE_NETWORK /&gt;
</text>


<text x="35" y="60" font-size="13">
root@madalitso-tech:~$ connect --secure
</text>


<text x="35" y="82" font-size="12">
Initializing cyber cafe server...
</text>


<text x="35" y="104" font-size="12">
IP: 192.168.1.254  STATUS: ONLINE
</text>


<text x="540" y="40" font-size="14">
MADALITSO SAULOS
</text>


<text x="540" y="65" font-size="12">
TECH SPACE // NETWORK HUB
</text>


<text x="540" y="90" font-size="12">
Firewall: ACTIVE
</text>


<text x="540" y="110" font-size="12">
Encryption: AES-256
</text>


</g>



<!-- Center Logo -->

<text x="250" y="280"
fill="#00ffff"
font-size="18"
font-family="monospace"
filter="url(#glow)">
CYBERCAFE MADALITSO SAULOS TECH SPACE
</text>



<!-- Status -->

<circle cx="740" cy="240" r="15"
stroke="#00ffff"
stroke-width="3"
fill="none">

<animate attributeName="r"
values="15;25;15"
dur="1.5s"
repeatCount="indefinite"/>

</circle>


<text x="680" y="280"
fill="#00ffff"
font-size="14"
font-family="monospace">
ONLINE
</text>


</svg>
