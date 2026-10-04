---
marp: true
theme: default
paginate: true

<style>
section {
  background: #ffffff;
  font-family: Arial, sans-serif;
}

h1 {
  color: #174a2b;
  font-size: 34px;
  margin-bottom: 10px;
}

h2 {
  color: #333;
  font-size: 22px;
}

/* =========================================================
   STYLES DU PLAN
   ========================================================= */

.plan {
  width: 100%;
  height: 650px;
}

.terrain {
  fill: none;
  stroke: #777;
  stroke-width: 2;
}

.parcelle {
  fill: none;
  stroke: #aaa;
  stroke-width: 1.5;
}

.quartier {
  fill: none;
  stroke: #ddd;
  stroke-width: 1;
}

.pe25 {
  fill: none;
  stroke: #0066cc;
  stroke-width: 14;
  stroke-linecap: round;
  stroke-linejoin: round;
}

.pe25-principal {
  stroke-width: 20;
}

.vanne-generale {
  fill: #d62828;
  stroke: #fff;
  stroke-width: 4;
}

.collecteur {
  fill: #d62828;
  stroke: #fff;
  stroke-width: 3;
}

.vanne-parcelle {
  fill: #36a64f;
  stroke: #fff;
  stroke-width: 3;
}

.label {
  font-size: 18px;
  font-weight: bold;
  fill: #333;
}

.label-eau {
  fill: #0066cc;
}

.label-vanne {
  fill: #d62828;
}

.label-collecteur {
  fill: #d62828;
}

.label-parcelle {
  font-size: 16px;
  fill: #555;
}

/* =========================================================
   VISIBILITE DES ETAPES
   ========================================================= */

/* Par défaut, toutes les étapes sont masquées */
.etape-1,
.etape-2,
.etape-3 {
  display: none;
}

/* Slide étape 1 */
.etape-1-visible .etape-1 {
  display: inline;
}

/* Slide étape 2 */
.etape-2-visible .etape-1,
.etape-2-visible .etape-2 {
  display: inline;
}

/* Slide étape 3 */
.etape-3-visible .etape-1,
.etape-3-visible .etape-2,
.etape-3-visible .etape-3 {
  display: inline;
}

/* =========================================================
   LEGENDE
   ========================================================= */

.legende {
  position: absolute;
  right: 40px;
  bottom: 35px;
  font-size: 17px;
  line-height: 1.6;
}

.legende-ligne {
  display: flex;
  align-items: center;
  gap: 10px;
}

.legende-bleu {
  width: 35px;
  height: 8px;
  background: #0066cc;
  border-radius: 5px;
}

.legende-rouge {
  width: 14px;
  height: 14px;
  background: #d62828;
  border-radius: 50%;
}

.legende-vert {
  width: 14px;
  height: 14px;
  background: #36a64f;
  transform: rotate(45deg);
}

/* =========================================================
   TITRE ET BADGE
   ========================================================= */

.etape {
  display: inline-block;
  padding: 5px 14px;
  border-radius: 15px;
  background: #174a2b;
  color: white;
  font-size: 16px;
  font-weight: bold;
}

.description {
  margin-top: 5px;
  margin-bottom: 10px;
  color: #555;
}
</style>
---

# Étape 1 — Arrivée du réseau principal

<span class="etape">ÉTAPE 1</span>

**Arrivée PE25 → vanne générale**

<div class="description">
On amène le PE25 jusqu'au regard central et on installe la vanne générale.
</div>

<div class="etape-1-visible">

<svg class="plan"
     viewBox="0 0 1389 1384"
     xmlns="http://www.w3.org/2000/svg">

  <!-- ================= TERRAIN ================= -->

  <g class="terrain">

    <!-- Cercle extérieur -->
    <path d="M698 2
             C1079.0765 2 1388 310.9235 1388 692
             C1388 1073.0765 1079.0765 1382 698 1382
             C316.9235 1382 8 1073.0765 8 692
             C8 310.9235 316.9235 2 698 2Z"/>

    <!-- Carré -->
    <path d="M8 2
             C468 2 928 2 1388 2
             C1388 462 1388 922 1388 1382
             C928 1382 468 1382 8 1382
             C8 922 8 462 8 2Z"/>

    <!-- Parcelles -->
    <path class="parcelle" d="M620 1H770V351H620Z"/>
    <path class="parcelle" d="M975.5481 54.9456
             L1105.4519 129.9456
             L930.4519 433.0544
             L800.5481 358.0544Z"/>
    <path class="parcelle" d="M1255.0544 278.5481
             L1330.0544 408.4519
             L1026.9456 583.4519
             L951.9456 453.5481Z"/>
    <path class="parcelle" d="M1038 617H1388V767H1038Z"/>
    <path class="parcelle" d="M1038 819H1388V969H1038Z"/>
    <path class="parcelle" d="M620 1032H770V1382H620Z"/>

    <!-- Cercle central -->
    <circle cx="698" cy="692" r="100"/>

  </g>


  <!-- ================= ÉTAPE 1 ================= -->

  <g class="etape-1">

    <!-- Arrivée PE25 -->
    <line class="pe25 pe25-principal"
          x1="1346" y1="1340"
          x2="860" y2="852"/>

    <!-- arrivée -->
    <circle class="vanne-generale"
            cx="1340" cy="1340" r="12"/>

    <!-- vanne générale -->
    <circle class="vanne-generale"
            cx="850" cy="850" r="16"/>

    <text class="label label-eau"
          x="1160" y="1325">
      ARRIVÉE PE25
    </text>

    <text class="label label-vanne"
          x="870" y="845">
      VANNE GÉNÉRALE
    </text>

  </g>

</svg>

</div>

<div class="legende">

<div class="legende-ligne">
<span class="legende-bleu"></span>
PE25
</div>

<div class="legende-ligne">
<span class="legende-rouge"></span>
Vanne
</div>

</div>


---

# Étape 2 — Distribution vers AQ1

<span class="etape">ÉTAPE 2</span>

**Vanne générale → collecteur AQ1**

<div class="description">
Depuis la vanne générale, le PE25 rejoint le premier collecteur de quartier.
</div>

<div class="etape-2-visible">

<svg class="plan"
     viewBox="0 0 1389 1384"
     xmlns="http://www.w3.org/2000/svg">

  <!-- TERRAIN -->

  <g class="terrain">

    <path d="M698 2
             C1079.0765 2 1388 310.9235 1388 692
             C1388 1073.0765 1079.0765 1382 698 1382
             C316.9235 1382 8 1073.0765 8 692
             C8 310.9235 316.9235 2 698 2Z"/>

    <path d="M8 2
             C468 2 928 2 1388 2
             C1388 462 1388 922 1388 1382
             C928 1382 468 1382 8 1382
             C8 922 8 462 8 2Z"/>

    <path class="parcelle"
          d="M620 1H770V351H620Z"/>

    <path class="parcelle"
          d="M975.5481 54.9456
             L1105.4519 129.9456
             L930.4519 433.0544
             L800.5481 358.0544Z"/>

    <path class="parcelle"
          d="M1255.0544 278.5481
             L1330.0544 408.4519
             L1026.9456 583.4519
             L951.9456 453.5481Z"/>

    <path class="parcelle"
          d="M1038 617H1388V767H1038Z"/>

    <path class="parcelle"
          d="M1038 819H1388V969H1038Z"/>

    <path class="parcelle"
          d="M620 1032H770V1382H620Z"/>

    <circle cx="698" cy="692" r="100"/>

  </g>


  <!-- ÉTAPE 1 -->

  <g class="etape-1">

    <line class="pe25 pe25-principal"
          x1="1346" y1="1340"
          x2="860" y2="852"/>

    <circle class="vanne-generale"
            cx="1340" cy="1340" r="12"/>

    <circle class="vanne-generale"
            cx="850" cy="850" r="16"/>

    <text class="label label-eau"
          x="1160" y="1325">
      ARRIVÉE PE25
    </text>

    <text class="label label-vanne"
          x="870" y="845">
      VANNE GÉNÉRALE
    </text>

  </g>


  <!-- ÉTAPE 2 -->

  <g class="etape-2">

    <!-- PE25 vers AQ1 -->
    <line class="pe25"
          x1="850" y1="846"
          x2="698" y2="511"/>

    <!-- Collecteur AQ1 -->
    <circle class="collecteur"
            cx="698" cy="511"
            r="18"/>

    <text class="label label-collecteur"
          x="720" y="505">
      AQ1
    </text>

  </g>

</svg>

</div>

<div class="legende">

<div class="legende-ligne">
<span class="legende-bleu"></span>
PE25
</div>

<div class="legende-ligne">
<span class="legende-rouge"></span>
Collecteur
</div>

</div>


---

# Étape 3 — Distribution aux parcelles

<span class="etape">ÉTAPE 3</span>

**Collecteur AQ1 → P1 / P2 / P3**

<div class="description">
Trois départs PE25 alimentent les trois premières parcelles. Chaque parcelle reçoit sa propre vanne accessible.
</div>

<div class="etape-3-visible">

<svg class="plan"
     viewBox="0 0 1389 1384"
     xmlns="http://www.w3.org/2000/svg">

  <!-- ================= TERRAIN ================= -->

  <g class="terrain">

    <path d="M698 2
             C1079.0765 2 1388 310.9235 1388 692
             C1388 1073.0765 1079.0765 1382 698 1382
             C316.9235 1382 8 1073.0765 8 692
             C8 310.9235 316.9235 2 698 2Z"/>

    <path d="M8 2
             C468 2 928 2 1388 2
             C1388 462 1388 922 1388 1382
             C928 1382 468 1382 8 1382
             C8 922 8 462 8 2Z"/>

    <path class="parcelle"
          d="M620 1H770V351H620Z"/>

    <path class="parcelle"
          d="M975.5481 54.9456
             L1105.4519 129.9456
             L930.4519 433.0544
             L800.5481 358.0544Z"/>

    <path class="parcelle"
          d="M1255.0544 278.5481
             L1330.0544 408.4519
             L1026.9456 583.4519
             L951.9456 453.5481Z"/>

    <path class="parcelle"
          d="M1038 617H1388V767H1038Z"/>

    <path class="parcelle"
          d="M1038 819H1388V969H1038Z"/>

    <path class="parcelle"
          d="M620 1032H770V1382H620Z"/>

    <circle cx="698" cy="692" r="100"/>

  </g>


  <!-- ================= ÉTAPE 1 ================= -->

  <g class="etape-1">

    <line class="pe25 pe25-principal"
          x1="1346" y1="1340"
          x2="860" y2="852"/>

    <circle class="vanne-generale"
            cx="1340" cy="1340" r="12"/>

    <circle class="vanne-generale"
            cx="850" cy="850" r="16"/>

    <text class="label label-eau"
          x="1160" y="1325">
      ARRIVÉE PE25
    </text>

    <text class="label label-vanne"
          x="870" y="845">
      VANNE GÉNÉRALE
    </text>

  </g>


  <!-- ================= ÉTAPE 2 ================= -->

  <g class="etape-2">

    <line class="pe25"
          x1="850" y1="846"
          x2="698" y2="511"/>

    <circle class="collecteur"
            cx="698" cy="511"
            r="18"/>

    <text class="label label-collecteur"
          x="720" y="505">
      AQ1
    </text>

  </g>


  <!-- ================= ÉTAPE 3 ================= -->

  <g class="etape-3">

    <!-- AQ1 → P1 -->
    <line class="pe25"
          x1="698" y1="511"
          x2="865" y2="396"/>

    <!-- AQ1 → P2 -->
    <line class="pe25"
          x1="698" y1="511"
          x2="989" y2="519"/>

    <!-- AQ1 → P3 -->
    <line class="pe25"
          x1="698" y1="511"
          x2="1038" y2="692"/>


    <!-- Vannes de parcelles -->

    <!-- P1 -->
    <circle class="vanne-parcelle"
            cx="865" cy="396"
            r="13"/>

    <text class="label"
          x="885" y="390">
      VANNE P1
    </text>


    <!-- P2 -->
    <circle class="vanne-parcelle"
            cx="989" cy="519"
            r="13"/>

    <text class="label"
          x="1008" y="515">
      VANNE P2
    </text>


    <!-- P3 -->
    <circle class="vanne-parcelle"
            cx="1038" cy="692"
            r="13"/>

    <text class="label"
          x="1058" y="687">
      VANNE P3
    </text>

  </g>

</svg>

</div>

<div class="legende">

<div class="legende-ligne">
<span class="legende-bleu"></span>
PE25
</div>

<div class="legende-ligne">
<span class="legende-rouge"></span>
Collecteur
</div>

<div class="legende-ligne">
<span class="legende-vert"></span>
Vanne parcelle
</div>

</div>

---

# 🧾 Devis & liste des fournitures

<div style="
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  height:520px;
  text-align:center;
">

<div style="font-size:70px;">🛒</div>

<h2 style="font-size:34px; color:#174a2b;">
Liste des fournitures et devis
</h2>

<p style="font-size:22px; color:#555;">
Retrouver le détail des composants, quantités,<br>
références et estimations de prix.
</p>

<a href="https://docs.google.com/spreadsheets/d/1IG6-NwMydbvbAU9pFtlKcpi_Dn63J-0s70rrTP_EaZY/edit?usp=sharing"
   style="
     display:inline-block;
     margin-top:25px;
     padding:16px 32px;
     background:#174a2b;
     color:white;
     text-decoration:none;
     border-radius:10px;
     font-size:22px;
     font-weight:bold;
   ">
   Ouvrir le devis →
</a>

</div>
