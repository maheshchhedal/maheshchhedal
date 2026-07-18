<svg width="100%" height="auto" viewBox="0 0 1180 610" preserveAspectRatio="xMidYMid meet" xmlns="http://www.w3.org/2000/svg">
<defs>
  <style>
    .pill { transform-box: fill-box; transform-origin: center; transition: transform .2s ease; }
    .pill:hover { transform: scale(1.1); }
    .pill:hover .pillGlow { opacity: 1; }
    .social:hover { transform: scale(1.15); }
    .social { transform-box: fill-box; transform-origin: center; transition: transform .2s ease; }
    text { font-family: 'Courier New', ui-monospace, monospace; }
  </style>

  <linearGradient id="bg" x1="0" y1="0" x2="1" y2="1">
    <stop offset="0%" stop-color="#030712"/>
    <stop offset="100%" stop-color="#050a16"/>
  </linearGradient>

  <linearGradient id="accentGrad" x1="0%" y1="0%" x2="100%" y2="0%">
    <stop offset="0%" stop-color="#7C3AED"/>
    <stop offset="50%" stop-color="#22D3EE"/>
    <stop offset="100%" stop-color="#10B981"/>
    <animate attributeName="x1" values="0%;100%;0%" dur="8s" repeatCount="indefinite"/>
    <animate attributeName="x2" values="100%;200%;100%" dur="8s" repeatCount="indefinite"/>
  </linearGradient>

  <linearGradient id="asciiGrad" x1="0%" y1="0%" x2="100%" y2="100%">
    <stop offset="0%" stop-color="#22D3EE"/>
    <stop offset="50%" stop-color="#7C3AED"/>
    <stop offset="100%" stop-color="#10B981">
      <animate attributeName="offset" values="1;0.6;1" dur="6s" repeatCount="indefinite"/>
    </stop>
    <animate attributeName="x1" values="0%;60%;0%" dur="5s" repeatCount="indefinite"/>
    <animate attributeName="y1" values="0%;40%;0%" dur="7s" repeatCount="indefinite"/>
  </linearGradient>

  <linearGradient id="borderGrad" x1="0%" y1="0%" x2="100%" y2="100%">
    <stop offset="0%" stop-color="#7C3AED" stop-opacity="0.7"/>
    <stop offset="50%" stop-color="#22D3EE" stop-opacity="0.9"/>
    <stop offset="100%" stop-color="#10B981" stop-opacity="0.7"/>
    <animateTransform attributeName="gradientTransform" type="rotate" from="0 0.5 0.5" to="360 0.5 0.5" dur="10s" repeatCount="indefinite"/>
  </linearGradient>

  <radialGradient id="blobPurple" cx="50%" cy="50%" r="50%">
    <stop offset="0%" stop-color="#7C3AED" stop-opacity="0.35"/>
    <stop offset="100%" stop-color="#7C3AED" stop-opacity="0"/>
  </radialGradient>
  <radialGradient id="blobCyan" cx="50%" cy="50%" r="50%">
    <stop offset="0%" stop-color="#22D3EE" stop-opacity="0.3"/>
    <stop offset="100%" stop-color="#22D3EE" stop-opacity="0"/>
  </radialGradient>
  <radialGradient id="blobEmerald" cx="50%" cy="50%" r="50%">
    <stop offset="0%" stop-color="#10B981" stop-opacity="0.28"/>
    <stop offset="100%" stop-color="#10B981" stop-opacity="0"/>
  </radialGradient>

  <linearGradient id="scanGrad" x1="0" y1="0" x2="0" y2="1">
    <stop offset="0%" stop-color="#22D3EE" stop-opacity="0"/>
    <stop offset="50%" stop-color="#22D3EE" stop-opacity="0.18"/>
    <stop offset="100%" stop-color="#22D3EE" stop-opacity="0"/>
  </linearGradient>

  <linearGradient id="glassGrad" x1="0" y1="0" x2="0.3" y2="1">
    <stop offset="0%" stop-color="#ffffff" stop-opacity="0.06"/>
    <stop offset="40%" stop-color="#ffffff" stop-opacity="0.01"/>
    <stop offset="100%" stop-color="#ffffff" stop-opacity="0"/>
  </linearGradient>

  <filter id="glow" x="-60%" y="-60%" width="220%" height="220%">
    <feGaussianBlur stdDeviation="4" result="blur"/>
    <feMerge>
      <feMergeNode in="blur"/>
      <feMergeNode in="SourceGraphic"/>
    </feMerge>
  </filter>

  <filter id="glowSoft" x="-80%" y="-80%" width="260%" height="260%">
    <feGaussianBlur stdDeviation="8"/>
  </filter>

  <filter id="noiseFilter">
    <feTurbulence type="fractalNoise" baseFrequency="0.85" numOctaves="2" stitchTiles="stitch" result="noise"/>
    <feColorMatrix in="noise" type="matrix" values="0 0 0 0 1, 0 0 0 0 1, 0 0 0 0 1, 0 0 0 0.02 0"/>
  </filter>

  <clipPath id="outerClip">
    <rect x="0" y="0" width="1180" height="610" rx="28"/>
  </clipPath>
  <clipPath id="leftClip">
    <rect x="30" y="30" width="430" height="550" rx="20"/>
  </clipPath>
  <clipPath id="rightClip">
    <rect x="490" y="30" width="660" height="550" rx="20"/>
  </clipPath>
</defs>

<g clip-path="url(#outerClip)">
  <rect x="0" y="0" width="1180" height="610" fill="url(#bg)"/>

  <!-- floating background blobs -->
  <circle cx="150" cy="120" r="180" fill="url(#blobPurple)">
    <animate attributeName="cx" values="150;220;150" dur="14s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="120;180;120" dur="11s" repeatCount="indefinite"/>
  </circle>
  <circle cx="950" cy="500" r="220" fill="url(#blobCyan)">
    <animate attributeName="cx" values="950;870;950" dur="16s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="500;430;500" dur="13s" repeatCount="indefinite"/>
  </circle>
  <circle cx="700" cy="80" r="160" fill="url(#blobEmerald)">
    <animate attributeName="cx" values="700;780;700" dur="12s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="80;140;80" dur="10s" repeatCount="indefinite"/>
  </circle>

  <!-- noise overlay -->
  <rect x="0" y="0" width="1180" height="610" filter="url(#noiseFilter)"/>

  <!-- particles -->
  <g fill="#22D3EE">
    <circle cx="90" cy="500" r="2" opacity="0.5">
      <animate attributeName="cy" values="500;460;500" dur="6s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0.2;0.7;0.2" dur="6s" repeatCount="indefinite"/>
    </circle>
    <circle cx="380" cy="90" r="1.6" opacity="0.5" fill="#7C3AED">
      <animate attributeName="cy" values="90;140;90" dur="8s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0.15;0.6;0.15" dur="8s" repeatCount="indefinite"/>
    </circle>
    <circle cx="1080" cy="150" r="2" opacity="0.5" fill="#10B981">
      <animate attributeName="cy" values="150;200;150" dur="7s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0.2;0.6;0.2" dur="7s" repeatCount="indefinite"/>
    </circle>
    <circle cx="600" cy="560" r="1.8" opacity="0.4">
      <animate attributeName="cy" values="560;520;560" dur="9s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0.15;0.55;0.15" dur="9s" repeatCount="indefinite"/>
    </circle>
    <circle cx="1000" cy="70" r="1.6" opacity="0.4" fill="#7C3AED">
      <animate attributeName="cy" values="70;110;70" dur="10s" repeatCount="indefinite"/>
    </circle>
  </g>

  <!-- outer border shimmer -->
  <rect x="1.5" y="1.5" width="1177" height="607" rx="27" fill="none" stroke="url(#borderGrad)" stroke-width="1.5"/>

  <!-- ================= LEFT PANEL ================= -->
  <g>
    <rect x="30" y="30" width="430" height="550" rx="20" fill="#0F172A" fill-opacity="0.55" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <rect x="30" y="30" width="430" height="550" rx="20" fill="url(#glassGrad)"/>

    <g clip-path="url(#leftClip)">
      <!-- floating ascii block -->
      <g font-size="14.5" fill="url(#asciiGrad)" filter="url(#glow)" text-anchor="middle">
        <animateTransform attributeName="transform" type="translate" values="0,0; 0,-7; 0,0" dur="5s" repeatCount="indefinite" additive="sum"/>

        <text x="245" y="150">
          <tspan opacity="0">╔═══════════════╗<animate attributeName="opacity" values="0;0;1;1;0" keyTimes="0;0.02;0.08;0.88;1" dur="9s" begin="0.2s" repeatCount="indefinite"/></tspan>
        </text>
        <text x="245" y="172">
          <tspan opacity="0">║   ▓▓▓ SQL ▓▓▓ ║<animate attributeName="opacity" values="0;0;1;1;0" keyTimes="0;0.02;0.08;0.88;1" dur="9s" begin="0.4s" repeatCount="indefinite"/></tspan>
        </text>
        <text x="245" y="194">
          <tspan opacity="0">╚═══════════════╝<animate attributeName="opacity" values="0;0;1;1;0" keyTimes="0;0.02;0.08;0.88;1" dur="9s" begin="0.6s" repeatCount="indefinite"/></tspan>
        </text>
        <text x="245" y="222">
          <tspan opacity="0">╔═══════════════╗<animate attributeName="opacity" values="0;0;1;1;0" keyTimes="0;0.02;0.08;0.88;1" dur="9s" begin="0.8s" repeatCount="indefinite"/></tspan>
        </text>
        <text x="245" y="244">
          <tspan opacity="0">║   ░░░ ETL ░░░ ║<animate attributeName="opacity" values="0;0;1;1;0" keyTimes="0;0.02;0.08;0.88;1" dur="9s" begin="1.0s" repeatCount="indefinite"/></tspan>
        </text>
        <text x="245" y="266">
          <tspan opacity="0">╚═══════════════╝<animate attributeName="opacity" values="0;0;1;1;0" keyTimes="0;0.02;0.08;0.88;1" dur="9s" begin="1.2s" repeatCount="indefinite"/></tspan>
        </text>
        <text x="245" y="294">
          <tspan opacity="0">╔═══════════════╗<animate attributeName="opacity" values="0;0;1;1;0" keyTimes="0;0.02;0.08;0.88;1" dur="9s" begin="1.4s" repeatCount="indefinite"/></tspan>
        </text>
        <text x="245" y="316">
          <tspan opacity="0">║   ▒▒▒ AWS ▒▒▒ ║<animate attributeName="opacity" values="0;0;1;1;0" keyTimes="0;0.02;0.08;0.88;1" dur="9s" begin="1.6s" repeatCount="indefinite"/></tspan>
        </text>
        <text x="245" y="338">
          <tspan opacity="0">╚═══════════════╝<animate attributeName="opacity" values="0;0;1;1;0" keyTimes="0;0.02;0.08;0.88;1" dur="9s" begin="1.8s" repeatCount="indefinite"/></tspan>
        </text>
        <text x="245" y="366">
          <tspan opacity="0">    ┌───┴───┐<animate attributeName="opacity" values="0;0;1;1;0" keyTimes="0;0.02;0.08;0.88;1" dur="9s" begin="2.0s" repeatCount="indefinite"/></tspan>
        </text>
        <text x="245" y="388">
          <tspan opacity="0">    │  &gt;_   │<animate attributeName="opacity" values="0;0;1;1;0" keyTimes="0;0.02;0.08;0.88;1" dur="9s" begin="2.2s" repeatCount="indefinite"/></tspan>
        </text>
        <text x="245" y="410">
          <tspan opacity="0">    └───────┘<animate attributeName="opacity" values="0;0;1;1;0" keyTimes="0;0.02;0.08;0.88;1" dur="9s" begin="2.4s" repeatCount="indefinite"/></tspan>
        </text>

        <!-- blinking cursor -->
        <text x="245" y="432" font-size="16">
          <tspan opacity="1">█<animate attributeName="opacity" values="1;1;0;0" keyTimes="0;0.5;0.51;1" dur="1s" repeatCount="indefinite"/></tspan>
        </text>
      </g>

      <!-- scanline sweep -->
      <rect x="30" y="-40" width="430" height="50" fill="url(#scanGrad)">
        <animate attributeName="y" values="-40;580" dur="4.5s" repeatCount="indefinite"/>
      </rect>
    </g>

    <!-- top file label -->
    <text x="245" y="65" text-anchor="middle" font-size="11" fill="#94A3B8" letter-spacing="1">~/profile/avatar.ascii</text>

    <!-- status footer -->
    <g>
      <circle cx="215" cy="548" r="4" fill="#10B981">
        <animate attributeName="opacity" values="1;0.3;1" dur="2s" repeatCount="indefinite"/>
      </circle>
      <text x="228" y="552" font-size="12" fill="#94A3B8" letter-spacing="1">STATUS: ONLINE</text>
    </g>
  </g>

  <!-- ================= RIGHT PANEL (terminal) ================= -->
  <g>
    <rect x="490" y="30" width="660" height="550" rx="20" fill="#0F172A" fill-opacity="0.55" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <rect x="490" y="30" width="660" height="550" rx="20" fill="url(#glassGrad)"/>

    <!-- title bar -->
    <line x1="490" y1="70" x2="1150" y2="70" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>
    <circle cx="515" cy="50" r="6" fill="#FF5F56"/>
    <circle cx="538" cy="50" r="6" fill="#FFBD2E"/>
    <circle cx="561" cy="50" r="6" fill="#27C93F"/>
    <text x="820" y="55" text-anchor="middle" font-size="13" fill="#94A3B8">mahesh@dataeng: ~</text>

    <g clip-path="url(#rightClip)">
      <!-- greeting - typewriter reveal once -->
      <clipPath id="greetClip">
        <rect x="518" y="90" width="0" height="40">
          <animate attributeName="width" values="0;540" dur="1.6s" begin="0.3s" fill="freeze" calcMode="linear"/>
        </rect>
      </clipPath>
      <text x="518" y="118" font-size="27" font-weight="bold" fill="url(#accentGrad)" clip-path="url(#greetClip)">Hi 👋 I'm Mahesh Kumar Chhedal</text>
      <rect x="518" y="98" width="4" height="26" fill="#22D3EE">
        <animate attributeName="x" values="518;1058" dur="1.6s" begin="0.3s" fill="freeze" calcMode="linear"/>
        <animate attributeName="opacity" values="1;1;0;0" keyTimes="0;0.5;0.51;1" dur="1s" begin="1.9s" repeatCount="indefinite"/>
      </rect>

      <!-- role prompt -->
      <text x="518" y="152" font-size="15" fill="#64748B">$ whoami --role</text>

      <!-- cycling typed phrases -->
      <g font-size="19" fill="#22D3EE" font-weight="bold">
        <text x="518" y="182">
          <tspan opacity="0">&gt; Aspiring Data Engineer_
            <animate attributeName="opacity" values="0;1;1;0;0" keyTimes="0;0.02;0.16;0.18;1" dur="20s" begin="2s" repeatCount="indefinite"/>
          </tspan>
        </text>
        <text x="518" y="182">
          <tspan opacity="0">&gt; ETL Pipeline Builder_
            <animate attributeName="opacity" values="0;0;1;1;0;0" keyTimes="0;0.2;0.22;0.36;0.38;1" dur="20s" begin="2s" repeatCount="indefinite"/>
          </tspan>
        </text>
        <text x="518" y="182">
          <tspan opacity="0">&gt; PySpark &amp; Airflow Learner_
            <animate attributeName="opacity" values="0;0;1;1;0;0" keyTimes="0;0.4;0.42;0.56;0.58;1" dur="20s" begin="2s" repeatCount="indefinite"/>
          </tspan>
        </text>
        <text x="518" y="182">
          <tspan opacity="0">&gt; AWS Cloud Enthusiast_
            <animate attributeName="opacity" values="0;0;1;1;0;0" keyTimes="0;0.6;0.62;0.76;0.78;1" dur="20s" begin="2s" repeatCount="indefinite"/>
          </tspan>
        </text>
        <text x="518" y="182">
          <tspan opacity="0">&gt; Turning Data into Insights_
            <animate attributeName="opacity" values="0;0;1;1;0;0" keyTimes="0;0.8;0.82;0.96;0.98;1" dur="20s" begin="2s" repeatCount="indefinite"/>
          </tspan>
        </text>
      </g>

      <!-- info block -->
      <g font-size="15" fill="#F8FAFC">
        <text x="518" y="230" opacity="0">▸ Location: Nepal 🇳🇵
          <animate attributeName="opacity" values="0;1" begin="2.4s" dur="0.6s" fill="freeze"/>
        </text>
        <text x="518" y="258" opacity="0">▸ Education: BCA, Tribhuvan University (2025)
          <animate attributeName="opacity" values="0;1" begin="2.8s" dur="0.6s" fill="freeze"/>
        </text>
        <text x="518" y="286" opacity="0">▸ Current Focus: PySpark · Airflow · AWS
          <animate attributeName="opacity" values="0;1" begin="3.2s" dur="0.6s" fill="freeze"/>
        </text>
        <text x="518" y="314" opacity="0">▸ Portfolio: github.com/maheshchhedal
          <animate attributeName="opacity" values="0;1" begin="3.6s" dur="0.6s" fill="freeze"/>
        </text>
        <text x="518" y="342" opacity="0">▸ Email: reach out via GitHub profile
          <animate attributeName="opacity" values="0;1" begin="4.0s" dur="0.6s" fill="freeze"/>
        </text>
      </g>

      <!-- skills label -->
      <text x="518" y="382" font-size="13" fill="#94A3B8" letter-spacing="1">TECH STACK</text>

      <!-- skill pills row 1 -->
      <g font-size="13" font-weight="600">
        <g class="pill">
          <rect x="518" y="392" width="84" height="30" rx="15" fill="rgba(124,58,237,0.12)" stroke="#7C3AED" stroke-width="1"/>
          <rect class="pillGlow" x="518" y="392" width="84" height="30" rx="15" fill="none" stroke="#7C3AED" stroke-width="1" opacity="0" filter="url(#glowSoft)"/>
          <text x="560" y="412" text-anchor="middle" fill="#E9D5FF">Python</text>
        </g>
        <g class="pill">
          <rect x="616" y="392" width="57" height="30" rx="15" fill="rgba(34,211,238,0.12)" stroke="#22D3EE" stroke-width="1"/>
          <rect class="pillGlow" x="616" y="392" width="57" height="30" rx="15" fill="none" stroke="#22D3EE" stroke-width="1" opacity="0" filter="url(#glowSoft)"/>
          <text x="644" y="412" text-anchor="middle" fill="#A5F3FC">SQL</text>
        </g>
        <g class="pill">
          <rect x="687" y="392" width="84" height="30" rx="15" fill="rgba(16,185,129,0.12)" stroke="#10B981" stroke-width="1"/>
          <rect class="pillGlow" x="687" y="392" width="84" height="30" rx="15" fill="none" stroke="#10B981" stroke-width="1" opacity="0" filter="url(#glowSoft)"/>
          <text x="729" y="412" text-anchor="middle" fill="#A7F3D0">Pandas</text>
        </g>
        <g class="pill">
          <rect x="785" y="392" width="75" height="30" rx="15" fill="rgba(124,58,237,0.12)" stroke="#7C3AED" stroke-width="1"/>
          <rect class="pillGlow" x="785" y="392" width="75" height="30" rx="15" fill="none" stroke="#7C3AED" stroke-width="1" opacity="0" filter="url(#glowSoft)"/>
          <text x="822" y="412" text-anchor="middle" fill="#E9D5FF">NumPy</text>
        </g>
        <g class="pill">
          <rect x="874" y="392" width="93" height="30" rx="15" fill="rgba(34,211,238,0.12)" stroke="#22D3EE" stroke-width="1"/>
          <rect class="pillGlow" x="874" y="392" width="93" height="30" rx="15" fill="none" stroke="#22D3EE" stroke-width="1" opacity="0" filter="url(#glowSoft)"/>
          <text x="920" y="412" text-anchor="middle" fill="#A5F3FC">PySpark</text>
        </g>
      </g>

      <!-- skill pills row 2 -->
      <g font-size="13" font-weight="600">
        <g class="pill">
          <rect x="518" y="434" width="93" height="30" rx="15" fill="rgba(16,185,129,0.12)" stroke="#10B981" stroke-width="1"/>
          <rect class="pillGlow" x="518" y="434" width="93" height="30" rx="15" fill="none" stroke="#10B981" stroke-width="1" opacity="0" filter="url(#glowSoft)"/>
          <text x="564" y="454" text-anchor="middle" fill="#A7F3D0">Airflow</text>
        </g>
        <g class="pill">
          <rect x="625" y="434" width="57" height="30" rx="15" fill="rgba(124,58,237,0.12)" stroke="#7C3AED" stroke-width="1"/>
          <rect class="pillGlow" x="625" y="434" width="57" height="30" rx="15" fill="none" stroke="#7C3AED" stroke-width="1" opacity="0" filter="url(#glowSoft)"/>
          <text x="653" y="454" text-anchor="middle" fill="#E9D5FF">AWS</text>
        </g>
        <g class="pill">
          <rect x="696" y="434" width="84" height="30" rx="15" fill="rgba(34,211,238,0.12)" stroke="#22D3EE" stroke-width="1"/>
          <rect class="pillGlow" x="696" y="434" width="84" height="30" rx="15" fill="none" stroke="#22D3EE" stroke-width="1" opacity="0" filter="url(#glowSoft)"/>
          <text x="738" y="454" text-anchor="middle" fill="#A5F3FC">Docker</text>
        </g>
        <g class="pill">
          <rect x="794" y="434" width="57" height="30" rx="15" fill="rgba(16,185,129,0.12)" stroke="#10B981" stroke-width="1"/>
          <rect class="pillGlow" x="794" y="434" width="57" height="30" rx="15" fill="none" stroke="#10B981" stroke-width="1" opacity="0" filter="url(#glowSoft)"/>
          <text x="822" y="454" text-anchor="middle" fill="#A7F3D0">Git</text>
        </g>
        <g class="pill">
          <rect x="865" y="434" width="75" height="30" rx="15" fill="rgba(124,58,237,0.12)" stroke="#7C3AED" stroke-width="1"/>
          <rect class="pillGlow" x="865" y="434" width="75" height="30" rx="15" fill="none" stroke="#7C3AED" stroke-width="1" opacity="0" filter="url(#glowSoft)"/>
          <text x="902" y="454" text-anchor="middle" fill="#E9D5FF">MySQL</text>
        </g>
      </g>

      <!-- divider -->
      <line x1="518" y1="486" x2="1122" y2="486" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>

      <!-- social icons -->
      <g>
        <g class="social">
          <circle cx="545" cy="530" r="21" fill="rgba(255,255,255,0.04)" stroke="#94A3B8" stroke-width="1"/>
          <circle cx="545" cy="530" r="21" fill="none" stroke="#22D3EE" stroke-width="1" opacity="0.5" filter="url(#glowSoft)">
            <animate attributeName="opacity" values="0.2;0.6;0.2" dur="3s" repeatCount="indefinite"/>
          </circle>
          <text x="545" y="535" text-anchor="middle" font-size="12" fill="#F8FAFC" font-weight="bold">GH</text>
        </g>
        <g class="social">
          <circle cx="605" cy="530" r="21" fill="rgba(255,255,255,0.04)" stroke="#94A3B8" stroke-width="1"/>
          <circle cx="605" cy="530" r="21" fill="none" stroke="#7C3AED" stroke-width="1" opacity="0.5" filter="url(#glowSoft)">
            <animate attributeName="opacity" values="0.2;0.6;0.2" dur="3.4s" repeatCount="indefinite"/>
          </circle>
          <text x="605" y="535" text-anchor="middle" font-size="12" fill="#F8FAFC" font-weight="bold">in</text>
        </g>
        <g class="social">
          <circle cx="665" cy="530" r="21" fill="rgba(255,255,255,0.04)" stroke="#94A3B8" stroke-width="1"/>
          <circle cx="665" cy="530" r="21" fill="none" stroke="#10B981" stroke-width="1" opacity="0.5" filter="url(#glowSoft)">
            <animate attributeName="opacity" values="0.2;0.6;0.2" dur="3.8s" repeatCount="indefinite"/>
          </circle>
          <text x="665" y="535" text-anchor="middle" font-size="12" fill="#F8FAFC" font-weight="bold">X</text>
        </g>
        <g class="social">
          <circle cx="725" cy="530" r="21" fill="rgba(255,255,255,0.04)" stroke="#94A3B8" stroke-width="1"/>
          <circle cx="725" cy="530" r="21" fill="none" stroke="#22D3EE" stroke-width="1" opacity="0.5" filter="url(#glowSoft)">
            <animate attributeName="opacity" values="0.2;0.6;0.2" dur="4.2s" repeatCount="indefinite"/>
          </circle>
          <text x="725" y="535" text-anchor="middle" font-size="11" fill="#F8FAFC" font-weight="bold">WWW</text>
        </g>
      </g>
    </g>
  </g>
</g>
</svg>
