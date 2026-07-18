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

<path d="M380 150 L480 80 L580 140 L680 70 L780 150"/>
<path d="M480 80 L520 220 L580 140 L700 220 L780 150"/>
<path d="M580 140 L660 250"/>
<path d="M680 70 L700 220"/>

</g>



<!-- Network Nodes (smaller, shifted right) -->
<g fill="#00ffff" filter="url(#glow)">

<circle cx="380" cy="150" r="4">
<animate attributeName="r" values="4;7;4" dur="2s" repeatCount="indefinite"/>
</circle>

<circle cx="480" cy="80" r="4">
<animate attributeName="r" values="4;7;4" dur="2.5s" repeatCount="indefinite"/>
</circle>

<circle cx="580" cy="140" r="5">
<animate attributeName="r" values="5;8;5" dur="1.8s" repeatCount="indefinite"/>
</circle>

<circle cx="680" cy="70" r="4">
<animate attributeName="r" values="4;7;4" dur="2s" repeatCount="indefinite"/>
</circle>

<circle cx="780" cy="150" r="4">
<animate attributeName="r" values="4;7;4" dur="2s" repeatCount="indefinite"/>
</circle>

<circle cx="700" cy="220" r="4"/>

<circle cx="520" cy="220" r="4"/>

</g>



<!-- Barcode (small, added near top right) -->
<g fill="#00ffff" opacity="0.8">
  <rect x="620" y="15" width="2" height="20"/>
  <rect x="624" y="15" width="1" height="20"/>
  <rect x="627" y="15" width="3" height="20"/>
  <rect x="632" y="15" width="1" height="20"/>
  <rect x="635" y="15" width="2" height="20"/>
  <rect x="639" y="15" width="1" height="20"/>
  <rect x="642" y="15" width="3" height="20"/>
  <rect x="647" y="15" width="2" height="20"/>
  <rect x="651" y="15" width="1" height="20"/>
  <rect x="654" y="15" width="2" height="20"/>
  <rect x="658" y="15" width="1" height="20"/>
  <rect x="661" y="15" width="3" height="20"/>
  <rect x="666" y="15" width="1" height="20"/>
  <rect x="669" y="15" width="2" height="20"/>
</g>
<text x="685" y="30" fill="#00ffff" font-size="9" font-family="monospace" opacity="0.6">||</text>


<!-- Moving Data Packets -->
<circle r="3" fill="#00ffff">
<animateMotion dur="4s" repeatCount="indefinite">
<mpath href="#route"/>
</animateMotion>
</circle>

<path id="route" d="M380 150 L480 80 L580 140 L680 70 L780 150"
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
<circle cx="740" cy="240" r="12"
stroke="#00ffff"
stroke-width="3"
fill="none">

<animate attributeName="r"
values="12;20;12"
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
