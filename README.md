# radinovicux.github.io
<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PGW Quiz – Soziale Ungleichheit | Hamburg Abitur 2026</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:opsz,wght@9..40,300;9..40,400;9..40,500;9..40,600&display=swap" rel="stylesheet">
<style>
:root{--bg:#0f0e17;--sur:#1a1928;--sur2:#231f3a;--acc:#a78bfa;--acc2:#f472b6;--txt:#e8e6f0;--mut:#8b87a8;--brd:rgba(167,139,250,0.15);--ok:#34d399;--err:#f87171}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
body{font-family:'DM Sans',sans-serif;background:var(--bg);color:var(--txt);min-height:100vh;overflow-x:hidden}
body::before{content:'';position:fixed;top:-50%;left:-50%;width:200%;height:200%;background:radial-gradient(ellipse at 20% 20%,rgba(167,139,250,.07) 0%,transparent 50%),radial-gradient(ellipse at 80% 80%,rgba(244,114,182,.05) 0%,transparent 50%);animation:bg 20s ease-in-out infinite alternate;pointer-events:none;z-index:0}
@keyframes bg{0%{transform:translate(0,0)}100%{transform:translate(2%,2%)}}
body::after{content:'';position:fixed;inset:0;background-image:linear-gradient(rgba(167,139,250,.03) 1px,transparent 1px),linear-gradient(90deg,rgba(167,139,250,.03) 1px,transparent 1px);background-size:40px 40px;pointer-events:none;z-index:0}
.w{position:relative;z-index:1;max-width:720px;margin:0 auto;padding:0 20px}
header{padding:2rem 0 1.5rem;display:flex;align-items:center;justify-content:space-between}
.logo{font-family:'DM Serif Display',serif;font-size:1.3rem;color:var(--acc)}.logo span{color:var(--txt)}
.hbadge{font-size:11px;font-weight:500;letter-spacing:.08em;text-transform:uppercase;color:var(--mut);border:1px solid var(--brd);padding:5px 12px;border-radius:20px}
.screen{display:none}.screen.active{display:block}
/* START */
.hero{padding:3rem 0 2.5rem;text-align:center}
.eyebrow{font-size:11px;font-weight:600;letter-spacing:.15em;text-transform:uppercase;color:var(--acc);margin-bottom:1rem}
.hero h1{font-family:'DM Serif Display',serif;font-size:clamp(2.2rem,6vw,3.5rem);line-height:1.1;margin-bottom:.75rem}
.hero h1 em{font-style:italic;color:var(--acc)}
.hero-sub{font-size:15px;color:var(--mut);line-height:1.6;max-width:480px;margin:0 auto 2.5rem}
.stats{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-bottom:2.5rem}
.sc{background:var(--sur);border:1px solid var(--brd);border-radius:16px;padding:1.25rem 1rem;text-align:center}
.sc .n{font-family:'DM Serif Display',serif;font-size:2rem;color:var(--acc);display:block;line-height:1;margin-bottom:6px}
.sc .l{font-size:12px;color:var(--mut);font-weight:500}
.stitle{font-size:12px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;color:var(--mut);margin-bottom:12px}
.catgrid{display:grid;grid-template-columns:repeat(2,1fr);gap:10px;margin-bottom:2rem}
.cc{background:var(--sur);border:1px solid var(--brd);border-radius:14px;padding:14px 16px;cursor:pointer;transition:all .2s;text-align:left;display:flex;align-items:center;gap:12px}
.cc:hover{border-color:rgba(167,139,250,.4);background:var(--sur2)}
.cc.active{border-color:var(--acc);background:rgba(167,139,250,.08)}
.cc.active .cn{color:var(--acc)}
.cdot{width:10px;height:10px;border-radius:50%;flex-shrink:0}
.cn{font-size:13px;font-weight:500;color:var(--txt)}
.cct{font-size:11px;color:var(--mut);margin-top:2px}
.cc-all{grid-column:1/-1}
.drow{display:flex;gap:8px;margin-bottom:2rem;flex-wrap:wrap}
.db{background:var(--sur);border:1px solid var(--brd);border-radius:20px;padding:7px 16px;font-size:13px;font-family:'DM Sans',sans-serif;color:var(--mut);cursor:pointer;transition:all .2s}
.db:hover{color:var(--txt);border-color:rgba(167,139,250,.3)}
.db.active{color:var(--bg);font-weight:600}
.db[data-diff=all].active{background:var(--acc);border-color:var(--acc)}
.db[data-diff=leicht].active{background:var(--ok);border-color:var(--ok)}
.db[data-diff=mittel].active{background:#fbbf24;border-color:#fbbf24}
.db[data-diff=schwer].active{background:var(--err);border-color:var(--err)}
.sbtn{width:100%;background:var(--acc);color:var(--bg);border:none;border-radius:14px;padding:16px;font-size:16px;font-family:'DM Sans',sans-serif;font-weight:600;cursor:pointer;transition:all .2s;margin-bottom:2.5rem}
.sbtn:hover{opacity:.9;transform:translateY(-1px)}
/* QUIZ */
.qtop{display:flex;justify-content:space-between;align-items:center;padding:1.5rem 0 1rem}
.qctr{font-size:13px;color:var(--mut)}
.spill{font-size:13px;font-weight:600;color:var(--acc);background:rgba(167,139,250,.1);border:1px solid rgba(167,139,250,.2);padding:5px 14px;border-radius:20px}
.ptrack{height:3px;background:rgba(255,255,255,.06);border-radius:2px;overflow:hidden;margin-bottom:1.75rem}
.pfill{height:100%;background:linear-gradient(90deg,var(--acc),var(--acc2));border-radius:2px;transition:width .4s cubic-bezier(.4,0,.2,1)}
.qcard{background:var(--sur);border:1px solid var(--brd);border-radius:20px;padding:1.75rem;margin-bottom:1.25rem;animation:ci .3s ease}
@keyframes ci{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:translateY(0)}}
.qmeta{display:flex;align-items:center;gap:8px;margin-bottom:1rem;flex-wrap:wrap}
.cpill{font-size:11px;font-weight:600;letter-spacing:.06em;text-transform:uppercase;padding:4px 12px;border-radius:20px}
.dpill{font-size:11px;font-weight:600;padding:4px 10px;border-radius:20px}
.dl{background:rgba(52,211,153,.12);color:var(--ok)}
.dm{background:rgba(251,191,36,.12);color:#fbbf24}
.ds{background:rgba(248,113,113,.12);color:var(--err)}
.qtxt{font-size:17px;line-height:1.55;color:var(--txt);font-weight:400}
.ans{display:flex;flex-direction:column;gap:10px;margin-bottom:1rem}
.ab{background:var(--sur);border:1px solid rgba(255,255,255,.08);border-radius:14px;padding:14px 18px;font-size:14px;font-family:'DM Sans',sans-serif;color:var(--txt);cursor:pointer;text-align:left;transition:all .18s;line-height:1.5}
.ab:hover:not(.dis){border-color:rgba(167,139,250,.4);background:var(--sur2);transform:translateX(3px)}
.ab.ok{background:rgba(52,211,153,.1);border-color:var(--ok);color:var(--ok)}
.ab.no{background:rgba(248,113,113,.1);border-color:var(--err);color:var(--err)}
.ab.rv{background:rgba(167,139,250,.1);border-color:var(--acc);color:var(--acc)}
.ab.dis{pointer-events:none;opacity:.45}
.ab.ok.dis,.ab.no.dis,.ab.rv.dis{opacity:1}
.expl{background:var(--sur2);border:1px solid rgba(167,139,250,.12);border-left:3px solid var(--acc);border-radius:0 12px 12px 0;padding:14px 16px;font-size:13px;color:var(--mut);line-height:1.65;animation:fu .25s ease}
@keyframes fu{from{opacity:0;transform:translateY(4px)}to{opacity:1;transform:translateY(0)}}
.nxtbtn{width:100%;background:transparent;border:1px solid rgba(167,139,250,.3);border-radius:14px;padding:14px;font-size:14px;font-family:'DM Sans',sans-serif;font-weight:500;color:var(--acc);cursor:pointer;transition:all .2s;margin-top:12px;display:none}
.nxtbtn:hover{background:rgba(167,139,250,.08);border-color:var(--acc)}
/* RESULT */
.rh{text-align:center;padding:3rem 0 2rem}
.rg{font-family:'DM Serif Display',serif;font-size:5rem;line-height:1;margin-bottom:.5rem}
.rm{font-size:15px;color:var(--mut);margin-bottom:2rem}
.rs{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-bottom:2rem}
.crr{display:flex;align-items:center;gap:12px;margin-bottom:10px}
.crn{font-size:12px;color:var(--mut);width:165px;flex-shrink:0}
.cbt{flex:1;height:6px;background:rgba(255,255,255,.06);border-radius:3px;overflow:hidden}
.cbf{height:100%;border-radius:3px;transition:width .8s cubic-bezier(.4,0,.2,1)}
.crp{font-size:12px;font-weight:600;color:var(--txt);width:34px;text-align:right}
.rbtns{display:grid;grid-template-columns:1fr 1fr;gap:10px;padding-bottom:3rem}
.rbtn{padding:14px;border-radius:14px;font-size:14px;font-family:'DM Sans',sans-serif;font-weight:500;cursor:pointer;transition:all .2s;border:1px solid var(--brd);background:transparent;color:var(--txt)}
.rbtn.p{background:var(--acc);color:var(--bg);border-color:var(--acc);font-weight:600}
.rbtn:hover{opacity:.85}
footer{text-align:center;padding:1.5rem 0 2rem;font-size:12px;color:rgba(139,135,168,.5);border-top:1px solid var(--brd)}
@media(max-width:480px){.catgrid{grid-template-columns:1fr}.cc-all{grid-column:1}.rbtns{grid-template-columns:1fr}.hero h1{font-size:2rem}}
</style>
</head>
<body>
<div class="w">
<header>
  <div class="logo">PGW<span>Quiz</span></div>
  <div class="hbadge">Hamburg Abitur 2026</div>
</header>

<!-- START -->
<div id="s0" class="screen active">
  <div class="hero">
    <div class="eyebrow">Politik · Gesellschaft · Wirtschaft</div>
    <h1>Soziale<br><em>Ungleichheit</em></h1>
    <p class="hero-sub">120 anspruchsvolle Fragen für das Hamburger Abitur 2026 – alle Antwortmöglichkeiten sind bewusst schwer zu unterscheiden.</p>
  </div>
  <div class="stats">
    <div class="sc"><span class="n" id="tc">120</span><div class="l">Fragen</div></div>
    <div class="sc"><span class="n">5</span><div class="l">Kategorien</div></div>
    <div class="sc"><span class="n">3</span><div class="l">Levels</div></div>
  </div>
  <div class="stitle">Thema wählen</div>
  <div class="catgrid">
    <div class="cc cc-all active" data-cat="all"><div class="cdot" style="background:var(--acc)"></div><div><div class="cn">Alle Themen</div><div class="cct" id="c-all">120 Fragen</div></div></div>
    <div class="cc" data-cat="modelle"><div class="cdot" style="background:#a78bfa"></div><div><div class="cn">Sozialstrukturmodelle</div><div class="cct" id="c-modelle"></div></div></div>
    <div class="cc" data-cat="begriffe"><div class="cdot" style="background:#34d399"></div><div><div class="cn">Fachbegriffe</div><div class="cct" id="c-begriffe"></div></div></div>
    <div class="cc" data-cat="gerechtigkeit"><div class="cdot" style="background:#fbbf24"></div><div><div class="cn">Gerechtigkeitstheorien</div><div class="cct" id="c-gerechtigkeit"></div></div></div>
    <div class="cc" data-cat="sozialstaat"><div class="cdot" style="background:#f472b6"></div><div><div class="cn">Sozialstaat</div><div class="cct" id="c-sozialstaat"></div></div></div>
    <div class="cc" data-cat="analyse"><div class="cdot" style="background:#60a5fa"></div><div><div class="cn">Analyse &amp; Prüfung</div><div class="cct" id="c-analyse"></div></div></div>
  </div>
  <div class="stitle">Schwierigkeitsgrad</div>
  <div class="drow">
    <button class="db active" data-diff="all">Alle</button>
    <button class="db" data-diff="leicht">Leicht</button>
    <button class="db" data-diff="mittel">Mittel</button>
    <button class="db" data-diff="schwer">Schwer</button>
  </div>
  <button class="sbtn" onclick="startGame()">Quiz starten →</button>
</div>

<!-- QUIZ -->
<div id="s1" class="screen">
  <div class="qtop">
    <span class="qctr" id="qctr">Frage 1 / 120</span>
    <span class="spill" id="spill">0 richtig</span>
  </div>
  <div class="ptrack"><div class="pfill" id="pf" style="width:0%"></div></div>
  <div class="qcard">
    <div class="qmeta"><span class="cpill" id="cpill"></span><span class="dpill" id="dpill"></span></div>
    <p class="qtxt" id="qtxt"></p>
  </div>
  <div class="ans" id="ans"></div>
  <div id="expl"></div>
  <button class="nxtbtn" id="nxt" onclick="next()">Nächste Frage →</button>
</div>

<!-- RESULT -->
<div id="s2" class="screen">
  <div class="rh">
    <div class="rg" id="rg"></div>
    <div class="rm" id="rm"></div>
  </div>
  <div class="rs">
    <div class="sc"><span class="n" id="rc" style="color:var(--ok)">0</span><div class="l">Richtig</div></div>
    <div class="sc"><span class="n" id="rw" style="color:var(--err)">0</span><div class="l">Falsch</div></div>
    <div class="sc"><span class="n" id="rp">0%</span><div class="l">Score</div></div>
  </div>
  <div class="stitle">Nach Kategorie</div>
  <div id="catres" style="margin-bottom:2rem"></div>
  <div class="rbtns">
    <button class="rbtn p" onclick="startGame()">Nochmal spielen</button>
    <button class="rbtn" onclick="showS('s0')">Kategorie wählen</button>
  </div>
</div>

<footer>PGW Quiz · Soziale Ungleichheit · Hamburg Abitur 2026</footer>
</div>

<script>
/* ═══════════════════════════════════════════════════════════════
   FRAGENKATALOG – 120 Fragen, alle Distraktoren bewusst plausibel
   Designprinzip: jede falsche Antwort enthält einen wahren Kern,
   ist aber in einem entscheidenden Punkt falsch oder unvollständig.
═══════════════════════════════════════════════════════════════ */
const Q=[

/* ──────────────── SOZIALSTRUKTURMODELLE (25) ──────────────── */
{cat:"modelle",diff:"leicht",
q:"Was definiert bei Karl Marx die Klassenzugehörigkeit einer Person?",
a:["Die Höhe des monatlichen Einkommens und das Vermögen","Die Position im Herrschaftsgefüge – ob man befiehlt oder gehorcht","Das Verhältnis zu den Produktionsmitteln – ob man sie besitzt oder nicht","Das Bildungsniveau und der damit verbundene gesellschaftliche Status"],
c:2,
e:"Für Marx ist Klassenzugehörigkeit ausschließlich durch das Verhältnis zu den Produktionsmitteln bestimmt. Einkommen, Bildung und Herrschaft sind bei Marx Folgen dieser Eigentumsrelation, nicht ihre Ursache. Die Bourgeoisie besitzt Produktionsmittel, das Proletariat besitzt nur seine Arbeitskraft."},

{cat:"modelle",diff:"leicht",
q:"Dahrendorf entwickelte ein eigenes Klassenmodell als Kritik an Marx. Was ist die zentrale Grundlage seiner Klassenbildung?",
a:["Der Besitz von Produktionsmitteln, ergänzt um Bildung und Prestige","Herrschaftspositionen in institutionellen Verbänden – wer Befehlsgewalt hat vs. wer gehorcht","Das Einkommen in Verbindung mit dem Berufsprestige und der sozialen Herkunft","Kulturelle Wertorientierungen und Lebensstile innerhalb gesellschaftlicher Schichten"],
c:1,
e:"Dahrendorf löst Klasse vom Eigentum. Er betrachtet Herrschaft in organisierten Verbänden (Betriebe, Parteien, Vereinen) als Grundlage von Klassenbildung. Wer Befehlsgewalt innehat, gehört der herrschenden Klasse an – unabhängig davon, ob er Eigentümer ist."},

{cat:"modelle",diff:"leicht",
q:"Was ist das entscheidende Merkmal des Sinus-Milieu-Modells gegenüber klassischen Schichtmodellen?",
a:["Es misst ausschließlich Einkommens- und Bildungsunterschiede präziser als ältere Modelle","Es ergänzt die vertikale Dimension (soziale Lage) um eine horizontale (Wertorientierungen und Lebensstile)","Es analysiert gesellschaftliche Strukturen auf Grundlage von Herrschaftsverhältnissen, nicht Einkommen","Es zeigt, dass Klassen in modernen Gesellschaften vollständig durch Milieus ersetzt wurden"],
c:1,
e:"Schichtmodelle erfassen nur vertikale Hierarchien. Das Sinus-Modell fügt die horizontale Dimension hinzu: Lebensstile, Werte, Konsumgewohnheiten. Zwei Menschen derselben sozialen Lage können völlig verschiedenen Milieus angehören – etwa dem 'konservativ-etablierten' oder dem 'expeditiven' Milieu."},

{cat:"modelle",diff:"mittel",
q:"Max Weber ergänzt Marx' Klassenanalyse um weitere Dimensionen. Welche Aussage über Webers Schichtungstheorie ist korrekt?",
a:["Weber ersetzt den Klassenbegriff vollständig durch Stand und Partei, da Eigentum in der Moderne keine Rolle mehr spiele","Weber sieht Klasse, Stand und Partei als drei unabhängige Dimensionen, die nicht zwingend parallel verlaufen","Weber betrachtet Klasse und Stand als identisch und differenziert nur zwischen politischen Parteien als dritter Dimension","Weber gilt als erster Schichttheoretiker, der Klasse ausschließlich nach Bildung und Prestige definiert"],
c:1,
e:"Webers drei Dimensionen: Klasse (ökonomisch: Marktlage, Eigentum), Stand (soziale Schätzung, Prestige, Ehre) und Partei (politische Machtkämpfe). Sie sind unabhängig – ein reicher Emporkömmling hat Klassenmacht, aber keinen Stand; ein Adliger hat Stand, aber vielleicht keine Klassen­macht mehr."},

{cat:"modelle",diff:"mittel",
q:"Ulrich Beck beschreibt in der 'Risikogesellschaft' einen grundlegenden Wandel. Was ist seine Kernthese zur sozialen Ungleichheit?",
a:["Soziale Klassen werden in der Spätmoderne durch neue Risikogruppen ersetzt, die ausschließlich nach Umweltbelastung definiert sind","Traditionelle Klassen verlieren als kollektive Handlungseinheiten an Bindekraft; Individuen werden freigesetzt und müssen Risiken eigenverantwortlich tragen","Der Wohlfahrtsstaat hat Klassenungleichheiten so erfolgreich gemildert, dass sie gesellschaftlich nicht mehr relevant sind","Risikogesellschaft bedeutet, dass soziale Ungleichheit von der Produktionssphäre in die Konsumtionssphäre verlagert wurde"],
c:1,
e:"Beck: Individualisierung bedeutet nicht das Ende von Ungleichheit, sondern ihre Transformation. Klassenlagen verlieren Bindekraft als kollektive Identitäten. Individuen werden aus traditionellen Milieus freigesetzt und müssen ihre Biografie selbst gestalten. Risiken (Jobverlust, Scheidung, Krankheit) sind privatisiert, nicht mehr kollektiv abgefedert."},

{cat:"modelle",diff:"mittel",
q:"Welche der vier Aussagen zu Bourdieus Kapitalbegriffen ist korrekt?",
a:["Ökonomisches Kapital ist die wichtigste Kapitalform; kulturelles und soziales Kapital lassen sich stets in ökonomisches zurückführen","Inkorporiertes kulturelles Kapital umfasst Bildungszertifikate, weil diese im Körper als Wissen eingeschrieben sind","Soziales Kapital bezeichnet Ressourcen aus Netzwerken und Beziehungen, die bei Bedarf mobilisiert werden können","Objektiviertes kulturelles Kapital meint die durch Habitus verinnerlichten Geschmacksurteile und Sprachstile"],
c:2,
e:"Soziales Kapital = Ressourcen, die aus der Zugehörigkeit zu Gruppen und Netzwerken resultieren. Inkorporiertes kulturelles Kapital = verinnerlichte Fähigkeiten, Sprache, Geschmack (nicht Zertifikate). Objektiviertes kulturelles Kapital = materielle Kulturgüter (Bücher, Instrumente). Institutionalisiertes kulturelles Kapital = Bildungszertifikate."},

{cat:"modelle",diff:"mittel",
q:"Was meint Bourdieu mit 'Habitus'? Welche Aussage trifft den Begriff am präzisesten?",
a:["Der Habitus ist das akkumulierte ökonomische und kulturelle Kapital, das in sozialen Feldern eingesetzt wird","Der Habitus ist ein System dauerhafter, transponibler Dispositionen – durch frühe Sozialisation erzeugte Wahrnehmungs-, Urteils- und Handlungsschemata","Der Habitus bezeichnet die soziale Position im Raum, definiert durch Gesamtkapital und Kapitalstruktur","Der Habitus ist Bourdieus Begriff für die bewusste Strategie, mit der Akteure ihre Interessen in sozialen Feldern verfolgen"],
c:1,
e:"Der Habitus ist das 'Körper gewordene Soziale': nicht bewusste Strategie, sondern verinnerlichte, kaum reflektierbare Dispositionen. Er wird durch frühe Sozialisation erzeugt und strukturiert Geschmack, Körperhaltung, Sprache, Bildungsaspirationen – und reproduziert damit soziale Ungleichheiten, weil er als 'natürliche Begabung' erscheint."},

{cat:"modelle",diff:"mittel",
q:"Gerhard Schulzes 'Erlebnisgesellschaft' (1992) beschreibt einen gesellschaftlichen Wandel. Was ist sein zentrales Argument?",
a:["Moderne Gesellschaften sind durch Erlebnisarmut gekennzeichnet, weil Massenkonsum authentische Erfahrungen verdrängt","In wohlhabenden Gesellschaften wird die primäre Lebensorientierung von Überlebenssicherung auf subjektive Erlebnisqualität umgestellt – das Leben als ästhetisches Projekt","Erlebnismilieus ersetzen sozioökonomische Klassen als strukturierendes Prinzip moderner Ungleichheit vollständig","Der Erlebniskonsum führt zur Auflösung sozialer Unterschiede, weil alle Schichten gleiche Konsumgüter nutzen"],
c:1,
e:"Schulze: In der gesättigten Wohlstandsgesellschaft der BRD ist die Grundfrage nicht mehr 'Was brauche ich zum Leben?' sondern 'Was erlebe ich?' Das Projekt des schönen Lebens dominiert – mit neuen Milieuformen wie 'Niveaumilieu', 'Harmoniemilieu' oder 'Unterhaltungsmilieu', die sich nach Alter und Bildung unterscheiden."},

{cat:"modelle",diff:"schwer",
q:"Was bezeichnet Bourdieu mit 'symbolischer Gewalt'? Welche Formulierung trifft den Begriff am präzisesten?",
a:["Physische Gewaltandrohung durch sozial Überlegene, die durch kulturelle Normen legitimiert wird","Die Verfestigung von Herrschaft durch Massenmedien, die herrschende Interessen als allgemeine darstellen","Die sanfte, verkannte Herrschaft, die auf dem Einverständnis der Beherrschten beruht, weil beide Seiten die zugrundeliegenden Machtverhältnisse als legitim oder natürlich anerkennen","Der Einsatz von Bildungszertifikaten als Druckmittel, um soziale Auf- und Abstiege zu regulieren"],
c:2,
e:"Symbolische Gewalt (Bourdieu): besonders wirksam, weil unsichtbar. Herrschaft braucht keine physische Kraft, wenn die Beherrschten die Sichtweise der Herrschenden als 'natürlich' oder 'verdient' internalisiert haben. Bsp.: Arbeiterkinder erleben Bildungsmisserfolg als eigenes Versagen, nicht als strukturelle Benachteiligung. Beide Seiten erkennen die Machtasymmetrie nicht als solche."},

{cat:"modelle",diff:"schwer",
q:"Worin besteht der Unterschied zwischen Becks 'Individualisierung' und Reckwitz' 'Singularisierung'?",
a:["Beck beschreibt den Zerfall von Klassen durch Wohlstand; Reckwitz beschreibt denselben Prozess, betont aber stärker die politischen Konsequenzen","Beck analysiert die Freisetzung aus traditionellen Kollektiven; Reckwitz beschreibt darüber hinaus die gesellschaftliche Aufwertung des Einzigartigen als normativen Leitwert, der neue Ungleichheiten zwischen 'besonderer' und 'gewöhnlicher' Arbeit erzeugt","Individualisierung ist ein Merkmal der ersten Moderne (1960–1990), Singularisierung ein Merkmal der zweiten Moderne (ab 1990) – inhaltlich sind beide Begriffe identisch","Reckwitz kritisiert Becks Individualisierungsthese als zu optimistisch, weil Singularisierung zeige, dass Risiken kollektiv und nicht individuell getragen werden"],
c:1,
e:"Beck: Individuen werden aus Kollektiven freigesetzt, müssen Biografie selbst gestalten. Reckwitz geht weiter: Das Singuläre, Besondere, Unverwechselbare wird zum gesellschaftlichen Leitwert. Wer 'gewöhnlich' ist (Sachbearbeiter, Fließbandarbeiter), gilt als minderwertiger. Das erzeugt eine kulturelle Abwertung der 'alten Mitte' und schafft neue Spaltungen jenseits des Einkommens."},

{cat:"modelle",diff:"schwer",
q:"Was kritisiert die feministische Sozialwissenschaft an klassischen Schicht- und Klassenmodellen (Marx, Dahrendorf, Geißler)?",
a:["Die Modelle seien zu stark auf Bildung fixiert und unterschätzten die Bedeutung von Einkommen und Vermögen","Die Modelle verwendeten den Haushalt als Analyseeinheit und bestimmten seinen Status über die männliche Haupterwerbsperson – dadurch werde Geschlecht als eigenständige Ungleichheitsdimension systematisch unsichtbar","Die Modelle seien historisch überholt, weil sie auf dem Normalarbeitsverhältnis beruhten, das heute kaum noch existiert","Die Modelle ignorierten internationale Vergleiche und seien deshalb nur auf Deutschland anwendbar"],
c:1,
e:"Feministische Kritik (Ann Oakley, Joan Acker): Klassische Modelle definieren den Haushaltsstatus über den 'Haushaltsvorstand' (meist Mann). Dadurch werden geschlechtsspezifische Ungleichheiten (Lohnlücke, unbezahlte Sorgearbeit, Doppelbelastung, Karriereunterbrechungen) als eigenständige Strukturdimensionen ausgeblendet. Geschlecht wird nur als Attribut von Klasse behandelt, nicht als eigenständige Dimension."},

{cat:"modelle",diff:"schwer",
q:"Was meint Bourdieus Konzept des 'sozialen Raums'? Welche Aussage trifft zu?",
a:["Der soziale Raum ist ein Netzwerk von sozialen Beziehungen, das den Habitus einer Person bestimmt","Der soziale Raum ist ein mehrdimensionales Koordinatensystem: erste Achse = Gesamtkapitalvolumen, zweite Achse = Kapitalstruktur (welche Kapitalart dominiert) – Akteure mit ähnlicher Position haben ähnlichen Habitus ohne direkte Interaktion","Der soziale Raum bezeichnet den geografisch-städtischen Raum, in dem soziale Klassen wohnen und interagieren","Der soziale Raum ist das Feld der kulturellen Produktion, in dem Künstler und Intellektuelle um symbolisches Kapital kämpfen"],
c:1,
e:"Bourdieus sozialer Raum: Achse 1 = Kapitalvolumen (viel – wenig). Achse 2 = Kapitalstruktur (dominiert ökonomisches oder kulturelles Kapital?). Ein Universitätsprofessor und ein Manager haben ähnliches Gesamtkapital, aber verschiedene Strukturen: Professoren haben mehr kulturelles, Manager mehr ökonomisches Kapital. Diese Position erzeugt ähnlichen Habitus ohne Interaktion."},

{cat:"modelle",diff:"leicht",
q:"Was misst der Gini-Koeffizient, und welcher Wert beschreibt vollständige Gleichheit?",
a:["Er misst das Durchschnittseinkommen; 100 bedeutet vollständige Gleichheit","Er misst das Ausmaß der Einkommens- oder Vermögensungleichheit auf einer Skala von 0 bis 1; 0 bedeutet vollständige Gleichheit","Er misst den Anteil der Bevölkerung unter der Armutsgrenze; je näher an 0, desto höher die Armutsquote","Er misst die soziale Mobilität; ein Wert nahe 1 bedeutet hohe Durchlässigkeit der Gesellschaft"],
c:1,
e:"Gini-Koeffizient: 0 = vollständige Gleichheit (alle haben gleich viel), 1 = maximale Ungleichheit (eine Person hat alles). Deutschland: Einkommens-Gini nach Umverteilung ≈ 0,29, Vermögens-Gini ≈ 0,73 – Vermögensungleichheit ist deutlich höher als Einkommensungleichheit."},

{cat:"modelle",diff:"mittel",
q:"Was unterscheidet 'intragenerationale' von 'intergenerationaler' sozialer Mobilität?",
a:["Intragenerational = Mobilität innerhalb einer Gesellschaft; intergenerational = Mobilität zwischen verschiedenen Ländern","Intragenerational = Auf- oder Abstiege im eigenen Lebenslauf; intergenerational = Vergleich der sozialen Position zwischen Eltern und Kindern","Intragenerational = Mobilität innerhalb derselben Klasse; intergenerational = Mobilität zwischen verschiedenen Klassen","Intragenerational = kurzfristige Einkommensschwankungen; intergenerational = langfristige strukturelle Veränderungen"],
c:1,
e:"Intragenerational: Verändert sich die soziale Position einer Person im Verlauf ihres eigenen Lebens (Karrieremobilität)? Intergenerational: Erreichen Kinder eine andere soziale Position als ihre Eltern? Deutschland gilt im OECD-Vergleich als relativ immobil – die Herkunft prägt den Bildungs- und Berufsweg stark."},

{cat:"modelle",diff:"mittel",
q:"Das Sinus-Milieu-Modell wird regelmäßig aktualisiert. Was ist die methodische Grundlage für die Einteilung der Milieus?",
a:["Amtliche Statistiken zu Einkommen, Bildung und Beruf, die vom Sinus-Institut zu Milieus verdichtet werden","Empirische Befragungen und qualitative Interviews, die soziale Lage und Wertorientierungen kombinieren – das Modell wird regelmäßig aktualisiert, weil sich Werte verschieben","Primär Bildungsabschlüsse und Berufsgruppen, ergänzt durch subjektive Selbsteinschätzungen der Befragten","Ausschließlich Konsummuster und Mediennutzung, aus denen Wertorientierungen abgeleitet werden"],
c:1,
e:"Das Sinus-Institut kombiniert quantitative Befragungen (soziodemografische Merkmale) mit qualitativen Interviews (Wertorientierungen, Lebensstile, Alltagsästhetik). Das Modell wird aktualisiert, weil sich Milieus verschieben: Das 'traditionsverwurzelte Milieu' schrumpft, das 'expeditive Milieu' wächst. Derzeit ca. 10 Milieus in Deutschland."},

{cat:"modelle",diff:"schwer",
q:"Wie erklärt Bourdieu das Phänomen, dass Kinder aus Bildungsfamilien im Schulsystem bessere Ergebnisse erzielen, obwohl Schule formal meritokratisch ist?",
a:["Das Schulsystem benachteiligt Arbeiterkinder durch explizit diskriminierende Notengebung und bewusste Lehrerpräferenzen","Das inkorporierte kulturelle Kapital aus bildungsnahen Familien (elaborierter Sprachkode, kulturelle Praktiken, Selbstsicherheit) wird vom Schulsystem als 'natürliche Begabung' prämiert – soziale Herkunft erscheint so als individuelle Leistung","Bildungsfamilien verfügen über mehr ökonomisches Kapital für Nachhilfe – allein dadurch entsteht der Vorteil","Kinder aus Akademikerfamilien haben biologisch bedingt höhere Intelligenz, die sich in schulischen Leistungen niederschlägt"],
c:1,
e:"Bourdieus Erklärung für die 'Illusion der Chancengleichheit': Das Schulsystem behandelt alle formal gleich, bewertet aber Kompetenzen (Sprachstil, kulturelle Referenzen, elaborierter Kode), die Kinder aus bildungsnahen Familien durch Sozialisation mitbringen. Dieser Vorteil erscheint als individuelle Begabung. So wird soziale Reproduktion als meritokratische Selektion verkleidet."},

{cat:"modelle",diff:"schwer",
q:"Was versteht Reckwitz unter der 'neuen Mittelklasse' und welche gesellschaftliche Spaltung erzeugt sie?",
a:["Die neue Mittelklasse ist die traditionelle Mittelschicht aus Handwerkern und Facharbeitern, die durch Deindustrialisierung ihre Position verloren hat","Eine hochqualifizierte, kreativ-akademische Klasse, die Singularität als kulturelle Norm etabliert; dadurch entsteht eine Spaltung gegenüber der 'alten Mittelklasse' (Angestellte, Beamte) und den prekären Klassen","Die neue Mittelklasse bezeichnet in der Bundesrepublik die neuen Selbstständigen im Dienstleistungssektor","Eine politisch mobilisierte Klasse, die Rechtspopulismus als Reaktion auf kulturelle Abwertung entwickelt hat"],
c:1,
e:"Reckwitz: Die neue Mittelklasse (Akademiker, Kreative, urbane Wissensarbeiter) setzt Singularität als gesellschaftliche Norm. Wer in standardisierten Berufen arbeitet, gilt als austauschbar und kulturell minderwertig. Das erzeugt eine Spaltung: alte Mitte und Arbeiterklasse erfahren nicht nur ökonomische, sondern auch kulturelle Abwertung – Grundlage des 'Kulturkampfs' in westlichen Demokratien."},

{cat:"modelle",diff:"schwer",
q:"Was ist der Unterschied zwischen Bourdieus 'Feld' und Dahrendorfs 'institutionellem Verband'?",
a:["Bourdieu analysiert Felder im wirtschaftlichen Bereich; Dahrendorf analysiert Verbände in der Politik – beide Konzepte sind inhaltlich identisch","Bourdieus Feld ist ein relativ autonomer sozialer Raum mit eigenen Regeln, in dem um feldspezifisches Kapital gekämpft wird; Dahrendorfs institutioneller Verband ist primär Ort von Herrschaft und Gehorsamkeit, aus dem Interessengruppen entstehen","Beide Konzepte wurden unabhängig entwickelt und beschreiben dasselbe: Organisationen als Orte sozialer Ungleichheit","Bourdieus Feld ist makrosoziologisch, Dahrendorfs Verband ist mikrosoziologisch – methodisch schließen sie sich aus"],
c:1,
e:"Feld (Bourdieu): Ein relativ autonomer sozialer Raum (Kunstfeld, Wissenschaftsfeld, ökonomisches Feld) mit eigenen Regeln, Spieleinsätzen und Kapitalformen. Akteure kämpfen um feldspezifisches Kapital. Institutioneller Verband (Dahrendorf): Organisation, in der Herrschaft ausgeübt wird. Klassenbildung entsteht durch die Herrschaftsstruktur. Bourdieus Feldkonzept ist komplexer und erfasst auch kulturelle Hierarchisierung."},

{cat:"modelle",diff:"leicht",
q:"Was beschreibt 'soziale Reproduktion' als soziologisches Konzept?",
a:["Die biologische Fortpflanzung sozialer Gruppen und deren demografische Entwicklung","Mechanismen, durch die soziale Ungleichheiten stabil bleiben und von Generation zu Generation weitergegeben werden","Der Prozess, durch den soziale Normen und Werte durch Sozialisation an die nächste Generation vermittelt werden","Die Tendenz sozialer Gruppen, ihre Mitglieder durch interne Heiratsmärkte zu reproduzieren"],
c:1,
e:"Soziale Reproduktion meint: Ungleichheiten erhalten sich selbst. Bourdieus Erklärung: Übertragung von kulturellem (Habitus, Bildung), sozialem (Netzwerke) und ökonomischem (Vermögen) Kapital. Das Bildungssystem trägt zur Reproduktion bei, indem es soziale Herkunft als individuelle Leistung erscheinen lässt."},

{cat:"modelle",diff:"mittel",
q:"Was ist der 'Prekarisierungsprozess' und welche gesellschaftliche Bedeutung hat er?",
a:["Die Zunahme von Armut durch Kürzungen staatlicher Sozialleistungen im Rahmen von Sparpolitik","Die Ausweitung atypischer Beschäftigung und unsicherer Lebensverhältnisse, die ehemals stabil integrierte Gruppen in Zonen der Vulnerabilität verdrängt","Die Erosion des Bildungsniveaus durch Privatisierung des Schulsystems in westlichen Gesellschaften","Der Rückgang der Mittelschicht durch Konzentration von Vermögen in den oberen Dezilen"],
c:1,
e:"Prekarisierung (Robert Castel): Ausweitung von Zeitverträgen, Leiharbeit, Minijobs, Solo-Selbstständigkeit. Betroffen: Geringqualifizierte, Migranten, Frauen in Teilzeit, aber zunehmend auch früher stabile Gruppen (Handwerker, Facharbeiter). Castel beschreibt drei Zonen: Integration, Vulnerabilität, Ausgrenzung. Prekarisierung = Wanderung von Integration in Vulnerabilität."},

{cat:"modelle",diff:"schwer",
q:"Welche methodische Kritik wird am Sinus-Milieu-Modell aus sozialwissenschaftlicher Perspektive geübt?",
a:["Es sei zu stark von quantitativer Forschung geprägt und vernachlässige qualitative Tiefeninterviews","Es sei primär für Marktforschungs- und Werbezwecke entwickelt worden und daher theoretisch untertheoretisiert; zudem seien die Milieugrenzen empirisch vage und die Zuordnung von Personen zu Milieus reifiziere soziale Kategorien","Es sei zu sehr auf westdeutsche Gesellschaften ausgerichtet und könne ostdeutsche oder migrantische Milieus nicht erfassen","Es messe nur statische Eigenschaften von Personen und könne soziale Mobilität zwischen Milieus nicht abbilden"],
c:1,
e:"Wissenschaftliche Kritik am Sinus-Modell: 1) Marktforschungsursprung: Kategorien dienten ursprünglich der Konsumentenanalyse, nicht der Sozialstrukturtheorie. 2) Reifikation: Die Einteilung in Milieus schreibt Personen feste Eigenschaften zu. 3) Theoretische Schwäche: Kein klares Kausalmodell, warum Werte und Lagen zusammenhängen. 4) Trennschärfe: Milieugrenzen sind empirisch unscharf."},

{cat:"modelle",diff:"schwer",
q:"Was ist der 'Matthew-Effekt' und wie erklärt er Ungleichheitspersistenz?",
a:["Er beschreibt, wie religiöse Bindungen in der Mittelklasse Bildungserfolg begünstigen","Kumulative Vorteilsakkumulation: frühe Vorteile (bessere Schule, Förderung) erzeugen weitere Vorteile – kleine Anfangsunterschiede wachsen zu großen Ungleichheiten über den Lebensverlauf","Er beschreibt, wie soziale Netzwerke privilegierten Personen Zugang zu exklusiven Berufsfeldern verschaffen","Er erklärt, warum Armut sich selbst verfestigt, weil Arme keine Anreize zur Weiterbildung haben"],
c:1,
e:"Matthew-Effekt (Merton, nach Matthäus 25,29): Anfangsvorteile akkumulieren sich kumulativ. Kinder mit besserer Frühförderung entwickeln schneller Lesekompetenz → bessere Grundschulnoten → bessere Schulempfehlung → Gymnasium → Hochschule → höheres Einkommen. Kleine Startunterschiede werden durch kumulative Prozesse zu enormen Lebenschancen-Unterschieden."},

{cat:"modelle",diff:"mittel",
q:"Was meint 'Kapitalstruktur' in Bourdieus sozialem Raum und warum ist sie analytisch wichtig?",
a:["Das Verhältnis von Eigen- zu Fremdkapital eines Unternehmens, das Bourdieus wirtschaftliches Klassenmodell strukturiert","Das Mischungsverhältnis der verschiedenen Kapitalarten (ökonomisch, kulturell, sozial) bei konstantem Gesamtvolumen – es erklärt, warum Personen gleicher sozialer Position (z.B. Professoren und Manager) verschiedene Lebenstile und Geschmäcker haben","Die Zuordnung von Kapitaleigentum zu sozialen Gruppen im Marx'schen Sinne, von Bourdieu auf kulturelle Güter ausgeweitet","Das Volumen des kulturellen Kapitals im Verhältnis zum Gesamtkapital – je höher es ist, desto höher die soziale Position"],
c:1,
e:"Kapitalstruktur bei Bourdieu: Personen können gleich viel Gesamtkapital besitzen, aber es unterschiedlich zusammensetzen. Professorin: viel kulturelles, wenig ökonomisches Kapital. Manager: viel ökonomisches, wenig kulturelles Kapital. Diese Strukturunterschiede erklären verschiedene Habitus, Geschmäcker (Klassikkonzert vs. Golf) und politische Orientierungen trotz ähnlicher Gesamtressourcen."},

/* ──────────────── FACHBEGRIFFE (25) ──────────────── */
{cat:"begriffe",diff:"leicht",
q:"Was unterscheidet 'absolute' von 'relativer' Armut konzeptionell?",
a:["Absolute Armut ist messbar, relative Armut ist eine subjektive Selbsteinschätzung ohne empirischen Standard","Absolute Armut meint das Fehlen lebensnotwendiger Güter (Nahrung, Unterkunft); relative Armut meint ein Einkommen deutlich unter dem gesellschaftlichen Durchschnitt – definiert als unter 60% des Medianeinkommens in der EU","Absolute Armut betrifft Entwicklungsländer, relative Armut ist ein Problem ausschließlich wohlhabender Gesellschaften","Beide Konzepte messen dasselbe, absolute Armut ist jedoch die ältere internationale Bezeichnung"],
c:1,
e:"Absolute Armut: Mangel an physisch überlebenswichtigen Gütern (Welthunger, Obdachlosigkeit). Relative Armut: Einkommensposition weit unter dem gesellschaftlichen Durchschnitt – führt zu sozialer Ausgrenzung auch bei physischer Grundversorgung. EU: Armutsrisikoschwelle = 60% des Medianäquivalenzeinkommens. In Deutschland 2023: ca. 15–16% der Bevölkerung betroffen."},

{cat:"begriffe",diff:"leicht",
q:"Was versteht man unter 'vertikaler sozialer Ungleichheit', und wie grenzt sie sich von horizontaler Ungleichheit ab?",
a:["Vertikal = Unterschiede zwischen städtischen und ländlichen Gebieten; horizontal = Unterschiede zwischen sozialen Schichten","Vertikal = hierarchische Unterschiede entlang einer Oben-Unten-Achse (Einkommen, Bildung, Prestige); horizontal = Ungleichheiten quer zur Hierarchie zwischen Gruppen auf ähnlicher sozialer Ebene (z.B. nach Geschlecht, Ethnizität, Alter)","Vertikal = langfristige strukturelle Ungleichheiten; horizontal = kurzfristige situative Benachteiligungen","Vertikal = messbarer Ressourcenbesitz; horizontal = wahrgenommene Statusunterschiede ohne materiellen Hintergrund"],
c:1,
e:"Vertikale Ungleichheit: Wer hat mehr oder weniger? (Einkommen, Bildung, Prestige). Horizontale Ungleichheit: Frauen und Männer auf gleichem Einkommensniveau können unterschiedliche Lebenschancen haben (Gender Pay Gap, Doppelbelastung, Karrierehemmnisse). Beide Dimensionen müssen analytisch getrennt werden, weil sie verschiedene politische Interventionen erfordern."},

{cat:"begriffe",diff:"mittel",
q:"Was meint 'Meritokratie' als gesellschaftliches Ordnungsprinzip, und welches ist das stärkste soziologische Gegenargument?",
a:["Meritokratie = Herrschaft der Besten nach Bildungsabschluss; Gegenargument: Bildungsabschlüsse messen nicht Talent, sondern Fleiß","Meritokratie = Verteilung gesellschaftlicher Positionen und Belohnungen nach individueller Leistung; das stärkste Gegenargument: Leistung selbst ist durch Herkunft, natürliche Talente und Glück geprägt – niemand verdient seine Ausgangsbedingungen","Meritokratie = Chancengleichheit durch Bildung; Gegenargument: Bildungssysteme sind zu teuer und für viele unzugänglich","Meritokratie = liberales Gerechtigkeitsprinzip; Gegenargument: es verstößt gegen das Gleichheitsprinzip des Grundgesetzes"],
c:1,
e:"Meritokratie (Michael Young, 1958 – ursprünglich als Warnung formuliert): Verteilung nach Verdienst/Leistung. Soziologisches Gegenargument (Rawls, Cohen, Bourdieu): 'Leistung' hängt von natürlichen Talenten (nicht verdient) und sozialer Herkunft (Habitus, kulturelles Kapital) ab. Meritokratie verschleiert strukturelle Benachteiligung als individuelle Leistungsdifferenz."},

{cat:"begriffe",diff:"mittel",
q:"Was unterscheidet den bereinigten vom unbereinigten Gender Pay Gap, und warum bleibt auch der bereinigte Wert erklärungsbedürftig?",
a:["Unbereinigt = Unterschied im Stundenlohn; bereinigt = Unterschied im Jahreseinkommen – der bereinigte Wert ist immer höher","Unbereinigt = alle Lohnunterschiede ohne Kontrolle struktureller Faktoren (~18%); bereinigt = Unterschied nach Kontrolle von Arbeitszeit, Branche, Beruf (~6%) – der Rest ist nicht durch messbare Faktoren erklärbar und gilt als Hinweis auf direkte Diskriminierung","Unbereinigt = Unterschied im Bruttoentgelt; bereinigt = Unterschied nach Steuer- und Sozialabgaben","Der bereinigte GPG ist immer kleiner und zeigt, dass die meiste Ungleichheit durch freiwillige Berufswahl entsteht und daher gerecht ist"],
c:1,
e:"Unbereinigter GPG (~18%): alle Lohnunterschiede zwischen Männern und Frauen. Bereinigter GPG (~6–7%): nach Kontrolle von Teilzeitquote, Branche, Beruf, Qualifikation. Dieser Rest lässt sich nicht durch Produktivitätsunterschiede erklären und gilt als Hinweis auf direkte Lohndiskriminierung. Zudem ist die 'freiwillige' Berufswahl selbst durch geschlechtsspezifische Sozialisation geprägt."},

{cat:"begriffe",diff:"schwer",
q:"Was meint 'Intersektionalität' als analytisches Konzept, und warum ist es mehr als die Summe einzelner Diskriminierungsformen?",
a:["Intersektionalität meint die Überschneidung verschiedener sozialer Felder im Sinne Bourdieus","Intersektionalität beschreibt das kumulative Addieren mehrerer Diskriminierungsformen – wer Frau UND arm ist, leidet unter der Summe beider Benachteiligungen","Intersektionalität zeigt, dass verschiedene Ungleichheitsdimensionen (Klasse, Geschlecht, Ethnizität) sich nicht nur addieren, sondern in qualitativ neuen Diskriminierungsformen zusammenwirken, die weder durch Klasse noch durch Geschlecht allein erklärbar sind","Intersektionalität ist ein statistisches Verfahren zur gleichzeitigen Messung mehrerer Diskriminierungsformen"],
c:2,
e:"Crenshaw (1989): Schwarze Frauen erleiden Diskriminierungen, die weder von antirassistischen noch von feministischen Bewegungen erfasst werden, weil beide nur eine Dimension betrachten. Die Kombination erzeugt qualitativ Neues: spezifische Stereotypen, spezifische Ausschlussmechanismen. Intersektionalität = Interaktion, nicht Addition der Dimensionen."},

{cat:"begriffe",diff:"mittel",
q:"Was meint 'strukturelle Diskriminierung' im Unterschied zur direkten Diskriminierung?",
a:["Strukturelle = durch Gesetze verankerte Diskriminierung; direkte = informelle soziale Ablehnung durch Einzelpersonen","Direkte Diskriminierung = bewusste, explizite Ungleichbehandlung aufgrund eines Merkmals; strukturelle = Benachteiligung durch scheinbar neutrale Institutionen, Regeln oder Praktiken, die bestimmte Gruppen systematisch schlechter stellen, ohne individuelle Diskriminierungsabsicht","Strukturelle Diskriminierung existiert nur im Bildungssystem; direkte Diskriminierung ist ein Problem des Arbeitsmarkts","Beide Formen sind strafrechtlich gleich sanktionierbar und werden im Allgemeinen Gleichbehandlungsgesetz identisch behandelt"],
c:1,
e:"Strukturelle Diskriminierung: kein böser Wille nötig. Bsp.: Schriftliche, anonymisierte Prüfungen zeigen, dass nicht-anonyme Bewertungen Schüler mit Migrationshintergrund systematisch schlechter beurteilen. Bsp.: Einstellungsverfahren favorisieren Bewerber ohne sichtbare Merkmale (Audit-Studien). Das System produziert Diskriminierung, ohne dass einzelne Akteure diskriminieren wollen."},

{cat:"begriffe",diff:"leicht",
q:"Was beschreibt Dahrendorfs Konzept der 'Lebenschancen'?",
a:["Die statistische Lebenserwartung einer Person, die von Klasse, Geschlecht und Gesundheitsversorgung abhängt","Die Wahrscheinlichkeit, bestimmte Lebensformen zu realisieren – abhängig von Optionen (Wahlmöglichkeiten) und Ligaturen (sinngebenden Bindungen)","Die Summe der wirtschaftlichen Ressourcen, über die eine Person im Laufe des Lebens verfügen kann","Die durch staatliche Politik garantierten Grundrechte, die jedem Bürger formal zur Verfügung stehen"],
c:1,
e:"Dahrendorf (1979): Lebenschancen = Optionen × Ligaturen. Optionen = Wahlmöglichkeiten im Leben. Ligaturen = Bindungen (Familie, Religion, Gemeinschaft), die Entscheidungen sinnhaft machen. Ohne Ligaturen werden Optionen zur Last (Anomie). Ohne Optionen werden Ligaturen zur Falle. Soziale Ungleichheit = ungleiche Lebenschancen durch ungleiche Optionen bei gleichzeitig geschwächten Ligaturen."},

{cat:"begriffe",diff:"mittel",
q:"Was versteht man unter 'sozialer Exklusion', und was unterscheidet sie vom klassischen Armutsbegriff?",
a:["Soziale Exklusion ist das modernere Synonym für Armut – beide Begriffe beschreiben dieselbe Realität","Soziale Exklusion ist multidimensional: Sie erfasst den Ausschluss aus mehreren gesellschaftlichen Teilsystemen (Arbeit, Bildung, Gesundheit, soziale Netzwerke, politische Teilhabe) – Armut ist nur eine Dimension davon","Soziale Exklusion betrifft ausschließlich Migranten und ethnische Minderheiten; Armut ist ein allgemeines Schichtungsphänomen","Exklusion meint freiwilligen Rückzug aus der Gesellschaft; Armut bezeichnet den unfreiwilligen Ressourcenmangel"],
c:1,
e:"Armut (eindimensional): Einkommensmangel. Soziale Exklusion (Castel, EU-Konzept): mehrdimensional – kein Job, keine Bildung, kein Netzwerk, kein politisches Engagement, kein Zugang zu Gesundheitsversorgung. EU-Indikator AROPE: armutsgefährdet ODER materiell depriviert ODER in Haushalt mit sehr geringer Erwerbsintensität. Exklusion meint kumulative Ausgliederung."},

{cat:"begriffe",diff:"schwer",
q:"Was unterscheidet 'Armutsgefährdung' von 'materieller Deprivation' als Messkonzepte, und warum werden beide im EU-AROPE-Index kombiniert?",
a:["Beide messen dasselbe, werden aber kombiniert, um regionale Unterschiede zwischen EU-Ländern zu berücksichtigen","Armutsgefährdung = relatives Einkommenskonzept (unter 60% des nationalen Medians); Deprivation = absolutes Konzept, das fehlendes Zugang zu konkreten Gütern misst – kombiniert, weil jemand einkommensarm aber nicht depriviert sein kann (Eigenheim) oder depriviert aber nicht einkommensarm (hohes Einkommen, aber Schulden)","Armutsgefährdung ist ein quantitatives Konzept; Deprivation ist qualitativ – erst zusammen erfassen sie Armut vollständig","Deprivation misst nur Bildungsarmut; Armutsgefährdung misst alle Dimensionen sozialer Ausgrenzung"],
c:1,
e:"AROPE (At Risk Of Poverty Or Social Exclusion): EU-Standardindikator. 1) Armutsgefährdung: unter 60% des nationalen Medianeinkommens. 2) Schwere materielle Deprivation: fehlendes Zugang zu mind. 4 von 9 Gütern (z.B. Heizung, Fleisch täglich, Urlaub). 3) Sehr geringe Erwerbsintensität. Eine Person gilt als betroffen, wenn mindestens eine Bedingung zutrifft."},

{cat:"begriffe",diff:"leicht",
q:"Was ist der Unterschied zwischen 'Einkommens-' und 'Vermögensungleichheit', und welche ist in Deutschland ausgeprägter?",
a:["Einkommensungleichheit ist ausgeprägter, weil Vermögen durch den Sozialstaat bereits stark umverteilt wird","Einkommen = laufende Einnahmen; Vermögen = akkumulierte Bestände – Vermögensungleichheit ist deutlich höher (Gini ≈ 0,73) als Einkommensungleichheit (Gini ≈ 0,29), weil Vermögen vererbt wird und sich kumuliert","Beide sind in Deutschland gleich stark ausgeprägt, da das Steuer- und Transfersystem beide Dimensionen gleichwertig erfasst","Vermögensungleichheit ist geringer, weil das Wohneigentum breit gestreut ist und die Mittelschicht absichert"],
c:1,
e:"Deutschland: Einkommens-Gini nach Umverteilung ≈ 0,29 (OECD-Durchschnitt). Vermögens-Gini ≈ 0,73 – eine der höchsten in Europa. Das reichste 10% besitzt ca. 60% des Nettovermögens, das reichste 1% ca. 35%. Ursache: Vermögen wird vererbt und akkumuliert sich; Sozialstaat transferiert Einkommen, greift aber kaum in Vermögensverteilung ein."},

{cat:"begriffe",diff:"schwer",
q:"Was ist 'working poor' und warum zeigt das Konzept die Grenzen des Vollbeschäftigungsziels als sozialpolitisches Ziel auf?",
a:["Working Poor sind Personen, die Vollzeit arbeiten, aber trotzdem staatliche Unterstützung benötigen – das Phänomen zeigt, dass Arbeit immer weniger Sinn ergibt","Working Poor = trotz Beschäftigung unter der Armutsrisikoschwelle lebend – das zeigt, dass Erwerbsarbeit allein keine Armutsprävention ist, wenn Löhne zu niedrig sind oder Beschäftigung zu wenig Stunden umfasst","Working Poor zeigt, dass das Bürgergeld als Armutsfalle wirkt, weil Arbeit kaum mehr einbringt als Transferleistungen","Working Poor sind Personen, die durch mehrere Jobs trotzdem nicht ausreichend verdienen – nur Mindestlohnanpassungen könnten das Problem lösen"],
c:1,
e:"Working Poor: Beschäftigt, aber Haushaltseinkommen unter der Armutsrisikoschwelle. In Deutschland ca. 9–10% der Vollzeitbeschäftigten. Ursachen: Niedriglohnsektor, Minijobs, Teilzeit. Sozialpolitisch bedeutsam: das Ziel 'Erwerbsarbeit als bester Schutz vor Armut' gilt nicht mehr pauschal. Mindestlohn (seit 2015, 2024: 12,41€) soll Untergrenze setzen – kritische Frage: reicht er?"},

{cat:"begriffe",diff:"mittel",
q:"Was beschreibt der Begriff 'Niedriglohnsektor', und wie wird er abgegrenzt?",
a:["Alle Berufsgruppen ohne gesetzlichen Mindestlohn oder ohne Tarifvertrag","Alle Beschäftigungsverhältnisse, bei denen der Bruttostundenlohn weniger als zwei Drittel des nationalen Medianlohns beträgt","Alle Minijobs und geringfügigen Beschäftigungen unabhängig von der Lohnhöhe","Berufe mit besonders hohem Anteil an Frauen oder Migranten, definiert nach Arbeitsmarktstatistiken"],
c:1,
e:"Niedriglohnsektor: International standardisierte Definition: unter 2/3 des Medianlohns (Bruttoentgelt). In Deutschland ca. 20–22% der Beschäftigten – einer der höchsten Anteile in Westeuropa. Branchen: Einzelhandel, Gastronomie, Pflege, Reinigung. Der Mindestlohn soll eine Untergrenze setzen, schützt aber nicht alle (Minijobs, Praktika)."},

{cat:"begriffe",diff:"schwer",
q:"Was meint 'Prekarität' bei Robert Castel, und was unterscheidet sie von Armut?",
a:["Prekarität und Armut sind synonyme Begriffe, die Castel austauschbar verwendet","Prekarität bezeichnet eine Zone der Vulnerabilität zwischen gesellschaftlicher Integration und vollständiger Ausgrenzung – instabile Beschäftigung und geschwächte soziale Bindungen, ohne notwendigerweise arm im materiellen Sinne zu sein","Prekarität bezeichnet ausschließlich subjektive Unsicherheitsgefühle, Armut meint objektiven Ressourcenmangel","Prekarität betrifft nur Personen in befristeten Arbeitsverhältnissen; Armut ist ein breiteres Konzept"],
c:1,
e:"Castel (1995): Drei Zonen – Integration (stabile Arbeit, starke soziale Netze), Vulnerabilität (instabile Arbeit, geschwächte Netze), Ausgrenzung. Prekarisierung = Wanderung von Integration in Vulnerabilität. Jemand kann prekär beschäftigt sein, ohne arm zu sein (junger Akademiker im Zeitvertrag). Umgekehrt kann jemand arm, aber nicht prekär sein (Rentner mit geringer Rente, aber stabilem sozialem Netz)."},

{cat:"begriffe",diff:"leicht",
q:"Was ist 'soziale Mobilität', und welche zwei Grundtypen unterscheidet die Soziologie?",
a:["Soziale Mobilität = geografische Wanderungsbewegungen; vertikal = zwischen Regionen, horizontal = innerhalb derselben Region","Soziale Mobilität = Veränderungen der sozialen Position im Schichtungssystem; intragenerational = im eigenen Lebenslauf, intergenerational = im Vergleich zur Elterngeneration","Soziale Mobilität = die Fähigkeit des Sozialstaats, Aufstieg zu ermöglichen; stark = hohe Sozialausgaben, schwach = niedrige Sozialausgaben","Soziale Mobilität = Aufwärtsmobilität durch Bildung; Abwärtsmobilität gilt soziologisch nicht als Mobilität, sondern als Deklassierung"],
c:1,
e:"Soziale Mobilität: Intragenerational = Auf- oder Abstieg im eigenen Lebenslauf (z.B. Aufstieg vom Facharbeiter zum Meister). Intergenerational = Vergleich zwischen Eltern und Kindern (z.B. Kind von Arbeitern wird Akademiker). Deutschland: im OECD-Vergleich relativ immobil – Herkunft erklärt Bildungs- und Einkommenserfolg stark."},

{cat:"begriffe",diff:"mittel",
q:"Was beschreibt der Begriff 'PISA-Schock' im Kontext sozialer Ungleichheit?",
a:["Die Erkenntnis aus PISA-Studien, dass deutsche Schulen im internationalen Vergleich schlechte Lehrqualität aufweisen","Die Erkenntnis aus PISA 2000, dass Deutschland einen der stärksten Zusammenhänge zwischen sozialer Herkunft und Lesekompetenz unter OECD-Ländern aufweist – Herkunft entscheidet über Bildungserfolg stärker als in fast allen Vergleichsländern","Der Schock über die schlechten Durchschnittsergebnisse deutscher Schüler im internationalen Leistungsvergleich, der keine Verbindung zu sozialer Ungleichheit hat","Die Erkenntnis, dass Einwanderer­kinder in Deutschland besonders schlecht abschneiden – der Herkunftseffekt trifft nur diese Gruppe"],
c:1,
e:"PISA 2000: Deutschland erreichte im internationalen Vergleich nicht nur mittelmäßige Ergebnisse, sondern zeigte auch einen ungewöhnlich starken Zusammenhang zwischen sozialer Herkunft (Elternbildung, Berufsposition) und Schülerleistungen. Kinder aus dem untersten Herkunftsviertel lagen im Schnitt fast 3 Schuljahre hinter dem obersten Viertel. Das traf Kinder mit Migrationshintergrund besonders stark."},

{cat:"begriffe",diff:"schwer",
q:"Was meint das Konzept des 'elaborierten' vs. 'restringierten Sprachkodes' (Bernstein), und wie verknüpft es sich mit sozialer Ungleichheit?",
a:["Elaborierter Kode = Hochsprache der Oberschicht; restringierter Kode = Dialekte der Unterschicht – beide sind kommunikativ gleichwertig","Elaborierter Kode = kontextunabhängige, explizite Sprache; restringierter Kode = kontextgebundene, implizite Sprache – Schule verwendet elaborierten Kode, was Kinder aus Mittelschichtsfamilien begünstigt und Arbeiterkinder strukturell benachteiligt","Elaborierter Kode meint Fachsprache; restringierter Kode meint Umgangssprache – beide werden im Schulsystem gleich bewertet","Sprachkodes sind irrelevant für schulischen Erfolg, weil Lehrer alle Kinder gleich fördern sollten"],
c:1,
e:"Basil Bernstein (1960er/70er): Elaborierter Kode = explizit, formal, dekontextualisiert (Mittelschicht). Restringierter Kode = implizit, kontextgebunden, gestützt auf gemeinsames Wissen (Arbeiterklasse). Schule operiert mit elaboriertem Kode. Arbeiterkinder müssen einen fremden Kode erwerben; Mittelschichtskinder setzen in der Schule fort, was zu Hause normal ist. Verknüpfung zu Bourdieu: Kode ist Teil des inkorporierten kulturellen Kapitals."},

{cat:"begriffe",diff:"leicht",
q:"Was beschreibt das Konzept der 'Bildungsungleichheit' im Kern?",
a:["Unterschiede in der Qualität von Schulgebäuden und Lehrausstattung zwischen verschiedenen Schulen","Der statistisch messbare Zusammenhang zwischen sozialer Herkunft und Bildungserfolg, durch den Herkunft über Abschlüsse, Berufe und Einkommen mitentscheidet","Ungleiche Verteilung von Lehrkräften nach Qualifikation zwischen Gymnasien und Hauptschulen","Unterschiede in Bildungsausgaben zwischen Bundesländern, die zu ungleichen Bildungschancen führen"],
c:1,
e:"Bildungsungleichheit meint: Kinder aus niedrigen sozialen Schichten erzielen statistisch schlechtere Bildungsabschlüsse als Kinder aus höheren Schichten – nicht wegen mangelnder Intelligenz, sondern wegen struktureller Unterschiede in Förderung, Habitus, kulturellem Kapital und Ressourcen. PISA bestätigt das für Deutschland besonders ausgeprägt."},

{cat:"begriffe",diff:"mittel",
q:"Was ist der 'demografische Wandel', und welche zwei Haupttreiber hat er?",
a:["Zunahme von Einwanderung und die damit verbundene kulturelle Diversifizierung der Gesellschaft","Geburtenrückgang (Fertilität unter dem Reproduktionsniveau von 2,1) und steigende Lebenserwartung – die Gesellschaft altert bei gleichzeitig schrumpfender erwerbsfähiger Bevölkerung","Urbanisierung und Landflucht als struktureller Wandel der Bevölkerungsverteilung","Zunahme der Einpersonenhaushalte und Rückgang traditioneller Familienstrukturen"],
c:1,
e:"Demografischer Wandel: 1) Geburtenrate Deutschland ≈ 1,5 (unter 2,1 = Reproduktionsniveau). 2) Lebenserwartung steigt (Männer ≈ 78, Frauen ≈ 83 Jahre). Folge: Verhältnis Erwerbstätige zu Rentnern verschlechtert sich. Altenquotient: 2020 ca. 36 Rentner pro 100 Erwerbstätige; 2050 prognistiziert: ca. 55. Das belastet alle umlagefinanzierten Sozialversicherungen."},

{cat:"begriffe",diff:"schwer",
q:"Was meint das Konzept 'soziale Schließung' (Max Weber) und welche Formen nimmt es an?",
a:["Soziale Schließung = staatliche Maßnahme zur Armutsbekämpfung durch Schließung sozialer Lücken im Sozialsystem","Soziale Schließung = Strategien von Gruppen, ihren sozialen Raum nach außen zu schließen, um Ressourcen zu monopolisieren – usurpatorisch (Außenseiter versuchen einzudringen) oder exklusiv (Insider schließen Außenseiter aus)","Soziale Schließung = das Ende sozialer Mobilität in einer Gesellschaft ohne Aufstiegschancen","Soziale Schließung = der Rückzug der Oberschicht in geschlossene Wohngebiete als Reaktion auf Urbanisierung"],
c:1,
e:"Weber/Frank Parkin: Soziale Schließung als Strategie, Chancen und Ressourcen durch Ausschluss zu monopolisieren. Exklusive Schließung: bestehende Gruppen halten Außenseiter heraus (Berufslizenzen, Adelsstand, Heiratsnormen). Usurpatorische Schließung: Ausgeschlossene versuchen, in Privilegien einzudringen. Relevanz: erklärt Beharrlichkeit sozialer Ungleichheiten trotz formaler Chancengleichheit."},

/* ──────────────── GERECHTIGKEITSTHEORIEN (25) ──────────────── */
{cat:"gerechtigkeit",diff:"leicht",
q:"Was ist der Kernunterschied zwischen liberaler und egalitaristischer Gerechtigkeitskonzeption?",
a:["Liberalismus befürwortet staatliche Umverteilung durch progressive Besteuerung; Egalitarismus lehnt Steuern als Eingriff in Eigentumsrechte ab","Liberalismus betont Verfahrensgerechtigkeit – wenn die Regeln fair sind, sind Ergebnisse legitim; Egalitarismus betont Ergebnisgerechtigkeit – die Verteilung selbst muss gerecht sein","Liberalismus ist eine wirtschaftliche Theorie, Egalitarismus eine politische Theorie – beide beschreiben Gerechtigkeit aus verschiedenen Wissenschaftsperspektiven","Liberalismus gilt in der Soziologie als gerechter, weil er individuelle Freiheit sichert; Egalitarismus gilt als kollektivistisch"],
c:1,
e:"Entscheidender Unterschied: Liberal (Nozick, Hayek): Gerechtigkeit = faire Prozesse. Wenn niemand betrogen oder gezwungen wird, sind die Ergebnisse legitim, egal wie ungleich. Egalitaristisch (Rawls, Dworkin, Cohen): Gerechtigkeit = gerechte Verteilung. Selbst faire Prozesse können ungerechte Ergebnisse erzeugen, die korrigiert werden müssen."},

{cat:"gerechtigkeit",diff:"leicht",
q:"Was ist John Rawls' 'Schleier des Nichtwissens', und welches Prinzip leitet er daraus ab?",
a:["Der Schleier des Nichtwissens ist eine Metapher für staatliche Geheimhaltung von Informationen über soziale Ungleichheit","Gedankenexperiment: Personen wählen Gerechtigkeitsregeln ohne zu wissen, welche Position sie in der Gesellschaft einnehmen – daraus folgt das Differenzprinzip: Ungleichheiten sind nur legitim, wenn sie den am schlechtesten Gestellten nützen","Der Schleier beschreibt die Unfähigkeit politischer Akteure, faire Gesetze zu erlassen, weil sie ihre eigenen Interessen kennen","Das Gedankenexperiment zeigt, dass alle Menschen hinter dem Schleier Chancengleichheit wählen würden – also das liberale Prinzip bestätigt"],
c:1,
e:"Rawls (Theorie der Gerechtigkeit, 1971): Im Urzustand hinter dem Schleier kennt niemand seine Talente, Herkunft, Werte oder gesellschaftliche Position. Rationale Personen würden sich gegen das Risiko absichern, ganz unten zu landen. Ergebnis: 1) Gleiche Grundfreiheiten für alle. 2) Differenzprinzip: Ungleichheiten nur zulässig, wenn sie den Schwächsten nützen. 3) Faire Chancengleichheit."},

{cat:"gerechtigkeit",diff:"mittel",
q:"Was ist Nozicks 'Entitlement Theory' (Anspruchstheorie), und warum lehnt er Rawls' Differenzprinzip ab?",
a:["Nozick stimmt dem Differenzprinzip grundsätzlich zu, lehnt aber dessen Umsetzung durch staatliche Bürokratie ab","Nozick: Menschen haben absolute Ansprüche auf legitim erworbenes Eigentum – Umverteilung durch den Staat verletzt diese Rechte, auch wenn sie den Schwächsten nützen würde","Nozick lehnt Rawls ab, weil das Differenzprinzip zu wenig umverteilt und eine vollständige Gleichstellung fordern sollte","Nozick argumentiert, dass Rawls' Schleier des Nichtwissens unrealistisch sei, weil niemand seine Interessen wirklich vergessen kann"],
c:1,
e:"Nozick (Anarchie, Staat, Utopia, 1974): Drei Prinzipien – legitimer Erwerb, legitime Übertragung, Wiedergutmachung von Unrecht. Wenn Eigentum durch freie Transaktionen entstanden ist, sind Umverteilungen moralisch Diebstahl. Wilt-Chamberlain-Argument: Auch kleine freiwillige Transaktionen führen zu Ungleichheit – das wäre zu korrigieren nur durch dauerhafte Eingriffe in individuelle Freiheit."},

{cat:"gerechtigkeit",diff:"mittel",
q:"Was sagen Davis & Moore über die Funktion sozialer Ungleichheit, und was ist die stärkste konflikttheoretische Kritik?",
a:["Davis & Moore: Ungleichheit entsteht durch Ausbeutung; Kritik: Verteilung folge Machtinteressen, nicht Funktionalität – beide Seiten stimmen aber im Ergebnis überein","Davis & Moore: Ungleichheit ist ein Anreizsystem, das wichtige Positionen attraktiv macht; Konflikttheoretiker kritisieren: Wer über 'funktionale Wichtigkeit' entscheidet, ist selbst Machtakteur – Pflege und Erziehung sind funktional zentral, aber schlecht bezahlt","Davis & Moore: Ungleichheit ist das Ergebnis natürlicher Begabungsunterschiede; Kritik: Begabung ist sozial konstruiert","Davis & Moore und Konflikttheorie kommen zum selben Ergebnis, verwenden nur verschiedene Erklärungsansätze"],
c:1,
e:"Davis & Moore (1945): Gesellschaft braucht Anreize (Einkommen, Prestige), um schwierige, wichtige Rollen (Arzt, Richter) attraktiv zu machen. Konflikttheoretische Kritik (Tumin): 1) Wer definiert 'wichtig'? Die herrschende Klasse im eigenen Interesse. 2) Pflegekräfte und Erzieherinnen sind funktional zentral, aber schlecht entlohnt. 3) Vererbte Privilegien blockieren Talente, die Anreize gar nicht nötig haben."},

{cat:"gerechtigkeit",diff:"mittel",
q:"Was versteht Amartya Sen unter dem 'Befähigungsansatz' (Capability Approach), und wie unterscheidet er sich von ressourcenbasierten Ansätzen?",
a:["Sen ersetzt Ressourcen durch subjektives Wohlbefinden als Gerechtigkeitsmaßstab","Sen: Was zählt, sind nicht Ressourcen (Geld, Güter) oder Wohlbefinden, sondern reale Fähigkeiten und Freiheiten, die Menschen nutzen können – weil gleiche Ressourcen verschiedenen Menschen verschiedene Freiheiten ermöglichen","Sen stimmt ressourcenbasierten Ansätzen wie Rawls zu, ergänzt nur die internationale Perspektive für Entwicklungsländer","Sen: Capabilities sind ausschließlich wirtschaftliche Produktivitätspotenziale, die durch Bildung und Gesundheit gefördert werden müssen"],
c:1,
e:"Sen (Development as Freedom, 1999): Ressourcen sind instrumentell – was zählt, ist was Menschen damit tun können (functionings und capabilities). Eine Rollstuhlfahrerin braucht mehr Geld für dieselbe Mobilität. Martha Nussbaum entwickelte konkrete Liste zentraler Capabilities (Gesundheit, Bildung, Kontrolle über die eigene Umgebung etc.). Grundlage des UN Human Development Index (HDI)."},

{cat:"gerechtigkeit",diff:"schwer",
q:"Was meint Ronald Dworkins Unterscheidung von 'brute luck' und 'option luck', und welche Umverteilungskonsequenz folgt daraus?",
a:["Brute luck = Zufallserfolge durch Arbeit; option luck = strukturelle Chancen, die der Staat schaffen muss","Brute luck = Zufälle, für die niemand verantwortlich ist (Herkunft, Behinderung, Naturkatastrophe); option luck = Ergebnis eines bewusst eingegangenen Risikos – Ungleichheiten durch brute luck soll der Staat kompensieren, Ungleichheiten durch option luck sind legitim","Dworkin lehnt beide Konzepte als unpraktisch ab und fordert stattdessen eine Umverteilung nach dem Differenzprinzip","Brute luck = natürliche Talente; option luck = soziale Chancen – Dworkin fordert, beide zu nivellieren"],
c:1,
e:"Dworkin (Ressourcenegalitarismus): Ungleichheiten durch Pech (Krankheit, arme Herkunft, Naturkatastrophe) sind unverschuldet und müssen kompensiert werden. Ungleichheiten durch bewusst eingegangene Risiken (Aktienspekulation, unternehmerisches Risiko) sind legitim. Praktische Konsequenz: Versicherungsmodell – als ob alle im Urzustand Versicherungen gegen brute luck abschließen würden."},

{cat:"gerechtigkeit",diff:"schwer",
q:"Was kritisiert G.A. Cohen an Rawls' Differenzprinzip aus marxistischer Perspektive?",
a:["Cohen stimmt Rawls vollständig zu und gilt als sein wichtigster Verteidiger im anglophonen Raum","Cohen kritisiert: Das Differenzprinzip akzeptiert, dass Hochqualifizierte nur dann ihre Talente einsetzen, wenn sie belohnt werden – das ist ein moralischer Defekt, weil niemand seine natürlichen Talente verdient und Solidarität ein Ethos braucht, das über Anreize hinausgeht","Cohen lehnt Rawls ab, weil das Differenzprinzip zu stark umverteilt und das Prinzip der Selbsteigentümerschaft verletzt","Cohen und Nozick haben dieselbe Kritik an Rawls, obwohl sie von verschiedenen politischen Positionen ausgehen"],
c:1,
e:"Cohen (Rescuing Justice and Equality, 2008): Rawls' Differenzprinzip erlaubt Ungleichheiten, wenn sie die Schwächsten besser stellen. Aber das impliziert, dass Ärzte und Banker höhere Gehälter brauchen, um ihre Talente einzusetzen. Cohen: Das ist moralisch bedenklich – echte Gleichheit erfordert ein solidarisches Ethos, in dem Leistung unabhängig von Anreizen für die Gemeinschaft erbracht wird. Rawls' Fehler: er reguliert Institutionen, nicht individuelle Handlungen."},

{cat:"gerechtigkeit",diff:"leicht",
q:"Was meint 'Teilhabegerechtigkeit' als sozialpolitisches Leitprinzip?",
a:["Alle Bürger erhalten gleiche Anteile an staatlichen Unternehmen und öffentlichen Gütern","Gesellschaftliche Gerechtigkeit erfordert nicht nur Einkommensumverteilung, sondern reale Teilhabe an Bildung, Kultur, politischem Leben und gesellschaftlicher Gestaltung – unabhängig von Herkunft und Ressourcen","Teilhabegerechtigkeit = gleiches Wahlrecht für alle – das politische Grundprinzip der Demokratie","Teilhabegerechtigkeit = Bedarfsgerechtigkeit mit zusätzlichen kulturellen Partizipationsrechten"],
c:1,
e:"Teilhabegerechtigkeit: Umverteilung von Geld allein genügt nicht – es braucht reale Möglichkeiten zur Partizipation. Kinderarmut verhindert nicht nur Konsum, sondern Teilhabe an Bildung, Musik, Sport, politischem Engagement. Maßnahmen: Bildungsgutscheine, Schulsozialarbeit, Kita-Ausbau, Kulturelle Bildungsangebote. Kindergrundsicherung (2025) zielt darauf ab."},

{cat:"gerechtigkeit",diff:"mittel",
q:"Was versteht Nancy Fraser unter 'Anerkennung' als eigenständiger Gerechtigkeitsdimension?",
a:["Anerkennung = Respekt zwischen Individuen; Fraser beschreibt, wie persönliche Wertschätzung ungleich verteilt ist","Fraser: Neben materieller Umverteilung gibt es eine eigenständige Gerechtigkeitsdimension der kulturellen Wertschätzung – Missanerkennung (Entwertung, Unsichtbarkeit, Stigmatisierung) ist ein eigenständiges Unrecht, das nicht auf materielle Ungleichheit reduziert werden kann","Anerkennung ist für Fraser nur ein Instrument zur Erreichung materieller Umverteilung, nicht ein eigenständiges Ziel","Fraser übernimmt Axel Honneths Anerkennungstheorie und wendet sie unkritisch auf Fragen der sozialen Gerechtigkeit an"],
c:1,
e:"Fraser (Umverteilung oder Anerkennung?, 2003): Zweidimensionale Gerechtigkeitskonzeption. 1) Umverteilung: ökonomische Ungerechtigkeit. 2) Anerkennung: kulturelle Ungerechtigkeit (Missachtung, Entwertung, Stigmatisierung von Gruppen). Beide Dimensionen können in Spannung geraten: Anerkennungspolitik für Gruppen kann Klassensolidarität schwächen. Fraser fordert 'partizipatorische Parität' als integrativen Maßstab."},

{cat:"gerechtigkeit",diff:"schwer",
q:"Warum scheitert der Utilitarismus als Gerechtigkeitstheorie an der Verteilung von Grundrechten, und welche Alternative schlägt Rawls vor?",
a:["Utilitarismus scheitert, weil er Glück nicht messen kann; Rawls schlägt dagegen eine rein verfahrensbasierte Lösung vor","Utilitarismus kann die Opferung individueller Grundrechte rechtfertigen, wenn sie den Gesamtnutzen steigert – Rawls antwortet mit dem Vorrang der ersten Gerechtigkeitsprinzipien (gleiche Grundfreiheiten), die nicht gegen Nutzensummen aufgewogen werden können","Utilitarismus und Rawls kommen bei der Verteilung von Grundrechten zum selben Ergebnis, unterscheiden sich nur bei der Einkommensverteilung","Rawls ergänzt den Utilitarismus um den Schleier des Nichtwissens, der utilitaristische Grundstruktur bleibt aber erhalten"],
c:1,
e:"Rawls' Kritik: Utilitarismus könnte Sklaverei legitimieren, wenn sie dem Glück der Mehrheit dient. Das widerspricht dem intuitiven Gerechtigkeitsgefühl. Rawls' Lösung: Gerechtigkeitsprinzipien in lexikografischer Ordnung – zuerst: gleiche Grundfreiheiten (dürfen nicht verletzt werden). Dann: faire Chancengleichheit. Dann: Differenzprinzip. Grundrechte sind nicht handelbar gegen Nutzensummen."},

{cat:"gerechtigkeit",diff:"mittel",
q:"Was meint 'Generationengerechtigkeit', und welche zwei Zeitperspektiven sind dabei relevant?",
a:["Gleichbehandlung aller Altersgruppen in aktuellen Verteilungsfragen; nur die aktuelle Generation ist dabei relevant","Gerechtigkeit gegenüber zukünftigen Generationen (wir dürfen sie nicht schlechter stellen) und intragenerationale Gerechtigkeit (zwischen heutigen Altersgruppen, z.B. Rentner vs. Erwerbstätige)","Generationengerechtigkeit betrifft ausschließlich die Rentenfinanzierung und nicht Klimapolitik oder Staatsverschuldung","Generationengerechtigkeit ist ein Konzept ausschließlich der konservativen Sozialpolitik ohne theoretische Grundlage"],
c:1,
e:"Generationengerechtigkeit: 1) Intergenerational (zukunftsbezogen): heutige Entscheidungen (Klimawandel, Staatsschulden, Ressourcenverbrauch) dürfen zukünftige Generationen nicht unverhältnismäßig belasten. BVerfG 2021 (Klimaschutzbeschluss): zukünftige Generationen haben Grundrechte auf Handlungsfreiheit. 2) Intragenerational: Verteilungsgerechtigkeit zwischen heutigen Altersgruppen im Rentensystem."},

{cat:"gerechtigkeit",diff:"schwer",
q:"Was meint Iris Marion Young mit den 'fünf Gesichtern der Unterdrückung', und warum reicht distributive Gerechtigkeit allein nicht aus?",
a:["Young kritisiert Verteilungsgerechtigkeit und fordert stattdessen vollständige Gleichheit der Ergebnisse","Young identifiziert fünf Formen struktureller Unterdrückung (Ausbeutung, Marginalisierung, Machtlosigkeit, Kulturimperialismus, Gewalt), die nicht auf Ressourcenverteilung reduzierbar sind – distributive Modelle sehen nur Güter, nicht die institutionellen Strukturen, die Gruppen systematisch unterdrücken","Young stimmt Rawls in den Grundzügen zu, ergänzt nur kulturelle Aspekte als fünfte Dimension","Young definiert Unterdrückung als persönliche Willkürherrschaft einzelner über andere"],
c:1,
e:"Young (Justice and the Politics of Difference, 1990): Distributive Modelle fragen 'Wer hat was?' – das erfasst nicht, warum bestimmte Gruppen systematisch schlechter gestellt sind. Fünf Gesichter: 1) Ausbeutung (Mehrwertaneignung), 2) Marginalisierung (aus Produktionssphäre ausgeschlossen), 3) Machtlosigkeit (keine Entscheidungsgewalt), 4) Kulturimperialismus (eigene Kultur abgewertet), 5) Gewalt (systematisch bedroht). Gerechtigkeit muss institutionelle Strukturen verändern."},

{cat:"gerechtigkeit",diff:"leicht",
q:"Was meint 'Bedarfsgerechtigkeit', und welches sozialpolitische Instrument setzt sie exemplarisch um?",
a:["Bedarfsgerechtigkeit = jeder bekommt gleich viel, unabhängig von Bedarf oder Leistung; Instrument: Grundeinkommen","Bedarfsgerechtigkeit = Verteilung nach individuellem Bedarf: wer mehr braucht, erhält mehr Unterstützung; umgesetzt durch bedürftigkeitsgeprüfte Sozialleistungen wie Bürgergeld, Wohngeld oder Pflegeleistungen","Bedarfsgerechtigkeit = leistungsabhängige Verteilung mit Mindeststandards; Instrument: Mindestlohn","Bedarfsgerechtigkeit = Chancengleichheit für alle; Instrument: kostenlose Schulbildung"],
c:1,
e:"Bedarfsgerechtigkeit: Ressourcen werden nach Bedarf zugeteilt. Umsetzung: Bürgergeld (Grundsicherung für Bedürftige), Wohngeld (einkommensabhängig), Sozialhilfe, Pflegeversicherung (Leistungen nach Pflegegrad). Im Spannungsverhältnis zur Leistungsgerechtigkeit (ALG I: nach Beiträgen) und zur Gleichheit (Kindergeld: universell)."},

{cat:"gerechtigkeit",diff:"mittel",
q:"Was ist das 'Egalitarismusparadox' nach Alexis de Tocqueville?",
a:["Egalitarismus führt langfristig zu mehr Ungleichheit, weil er Leistungsanreize reduziert","In Gesellschaften, in denen Gleichheit als Norm gilt, wird verbleibende Ungleichheit als besonders unerträglich wahrgenommen – mehr Gleichheit erzeugt paradoxerweise mehr Empörung über Ungleichheit","Demokratische Gesellschaften neigen trotz Gleichheitsideologie zur Oligarchie, weil Reiche politischen Einfluss kaufen können","Egalitarismus ist ein theoretisch konsistentes Prinzip, das aber in der politischen Realität immer scheitert"],
c:1,
e:"Tocqueville (Demokratie in Amerika): In Aristokratien erscheint Ungleichheit natürlich – sie ist seit Generationen legitimiert. In demokratisch-egalitären Gesellschaften gilt Gleichheit als Norm. Jede verbleibende Ungleichheit erscheint als Normverletzung, als Skandal. Paradox: Je egalitärer die Gesellschaft wird, desto empfindlicher reagiert sie auf noch bestehende Ungleichheiten."},

{cat:"gerechtigkeit",diff:"schwer",
q:"Was unterscheidet 'kommutative' von 'distributiver' Gerechtigkeit (Aristoteles), und welche Relevanz hat die Unterscheidung heute?",
a:["Kommutative = Gerechtigkeit zwischen Staat und Bürger; distributive = Gerechtigkeit zwischen Bürgern untereinander","Kommutative Gerechtigkeit = Tauschgerechtigkeit: proportional gleicher Austausch zwischen Personen (Vertrag, Kauf); distributive Gerechtigkeit = angemessene Verteilung gesellschaftlicher Güter und Lasten nach einem Maßstab (Verdienst, Bedarf, Gleichheit)","Beide Konzepte sind in der modernen Sozialwissenschaft durch Rawls' Theorie der Gerechtigkeit ersetzt worden","Kommutative Gerechtigkeit betrifft Strafrecht; distributive Gerechtigkeit betrifft Steuerrecht – keine inhaltliche Überschneidung"],
c:1,
e:"Aristoteles' Unterscheidung: Kommutativ = gleicher Ausgleich in Tauschverhältnissen (Kauf, Strafe). Distributiv = angemessene Verteilung nach Proportionalität (jeder nach seinem Beitrag oder Verdienst). Heute: Kommutative Gerechtigkeit dominiert Markt- und Vertragsrecht; distributive Gerechtigkeit ist Grundlage aller Sozialpolitik-Debatten (Rawls, Nozick, Cohen). Die Spannung zwischen beiden strukturiert viele politische Konflikte."},

/* ──────────────── SOZIALSTAAT (25) ──────────────── */
{cat:"sozialstaat",diff:"leicht",
q:"Was ist das Bismarcksches Sozialversicherungsmodell, und auf welchen Prinzipien beruht es?",
a:["Beveridge-Modell (1942): steuerfinanzierte Universalversicherung für alle Bürger unabhängig von Beiträgen","Bismarck-Modell (1883 ff.): Pflichtversicherung auf Beitragsbasis, paritätisch finanziert (je 50% AN und AG), Leistungen beitragsäquivalent und an Erwerbsarbeit geknüpft","Das Bismarck-Modell kombiniert Steuern und Beiträge gleichgewichtig und sichert alle Bürger universal ab","Das Bismarck-Modell basiert auf dem Subsidiaritätsprinzip: der Staat springt nur ein, wenn private Vorsorge versagt"],
c:1,
e:"Bismarck (1883–1889): Erste staatliche Sozialversicherung weltweit. Merkmale: 1) Pflichtbeiträge von Arbeitnehmern und Arbeitgebern (paritätisch). 2) Leistungen beitragsäquivalent (höhere Beiträge → höhere Rente). 3) An Erwerbsarbeit geknüpft – Nicht-Erwerbstätige (historisch: Frauen) waren ursprünglich nicht abgesichert. Deutschland folgt bis heute diesem Modell."},

{cat:"sozialstaat",diff:"leicht",
q:"In welchem Artikel des Grundgesetzes ist das Sozialstaatsprinzip verankert, und was verpflichtet es den Staat zu tun?",
a:["Art. 1 GG (Menschenwürde) – der Staat muss ein Existenzminimum gewährleisten, weil Würde materielle Grundlagen erfordert","Art. 20 Abs. 1 GG – Deutschland ist ein sozialer Bundesstaat; das verpflichtet den Gesetzgeber zum sozialen Ausgleich, lässt ihm aber Gestaltungsspielraum","Art. 14 GG (Eigentum) – die Eigentumsgarantie enthält die Sozialbindung, aus der Umverteilungspflichten folgen","Art. 3 GG (Gleichheit) – aus dem Gleichheitsgrundsatz folgt unmittelbar das Recht auf gleiche materielle Ressourcen"],
c:1,
e:"Art. 20 Abs. 1 GG: 'Die Bundesrepublik Deutschland ist ein demokratischer und sozialer Bundesstaat.' Das Sozialstaatsprinzip ist nicht ins Detail ausformuliert – es gibt dem Gesetzgeber Spielraum, verpflichtet ihn aber zum sozialen Ausgleich. BVerfG 2010: Aus Art. 1 Abs. 1 (Menschenwürde) in Verbindung mit Art. 20 Abs. 1 folgt ein Grundrecht auf Gewährleistung des menschenwürdigen Existenzminimums."},

{cat:"sozialstaat",diff:"mittel",
q:"Was unterscheidet das 'Äquivalenzprinzip' vom 'Solidarprinzip' in der deutschen Sozialversicherung?",
a:["Äquivalenzprinzip = alle zahlen denselben Prozentsatz; Solidarprinzip = Reiche zahlen mehr, bekommen aber dieselben Leistungen","Äquivalenzprinzip = Leistungen richten sich nach geleisteten Beiträgen (mehr eingezahlt → mehr Rente); Solidarprinzip = alle tragen in eine gemeinsame Risikogemeinschaft ein, Leistungen richten sich nach Bedarf unabhängig von der Beitragshöhe","Äquivalenzprinzip gilt nur für private Versicherungen; das gesetzliche System folgt ausschließlich dem Solidarprinzip","Beide Prinzipien sind in der deutschen Sozialversicherung strikt getrennt und nie gemischt"],
c:1,
e:"Deutsche Sozialversicherung kombiniert beide: Rentenversicherung = stark äquivalent (30 Beitragsjahre → höhere Rente). Gesetzliche Krankenversicherung = stark solidarisch: Beitrag nach Einkommen (einkommensschwache zahlen weniger), Leistung nach medizinischem Bedarf (Chronischkranke erhalten mehr ohne höhere Beiträge). Das Zusammenspiel ermöglicht vertikalen Umverteilungseffekt."},

{cat:"sozialstaat",diff:"mittel",
q:"Welche Kernargumente bringen Liberale gegen staatliche Umverteilung vor?",
a:["Liberale befürworten moderate Umverteilung, lehnen nur exzessive Eingriffe ab – sie stützen sich auf das Differenzprinzip nach Rawls","Vier liberale Einwände: 1) Eigentumsrechte (Zwangsabgaben = Diebstahl nach Nozick); 2) Fehlanreize/Moral Hazard (Leistungsbereitschaft sinkt); 3) Informationsproblem (Staat weiß nicht, was effizient ist); 4) intergenerationale Gerechtigkeit (Schulden belasten Zukunft)","Liberale lehnen Umverteilung ab, weil sie das Wirtschaftswachstum hemmt – das ist ihr einziges Argument","Liberale lehnen nur direkte Transfers ab, befürworten aber steuerliche Umverteilung durch progressive Einkommensteuer"],
c:1,
e:"Liberale Kritik an Umverteilung: 1) Eigentumsrechte (Nozick): Zwangsabgaben verletzen individuelle Freiheit. 2) Moral Hazard (Hayek): Zu hohe Transferleistungen schaffen Abhängigkeit und reduzieren Eigenverantwortung. 3) Hayeks Informationsproblem: Der Staat kann Bedürfnisse nicht besser kennen als Märkte. 4) Zukunftslast: Schuldenfinanzierung belastet kommende Generationen."},

{cat:"sozialstaat",diff:"mittel",
q:"Was meint das 'Subsidiaritätsprinzip' im deutschen Sozialstaat, und in welchem Spannungsverhältnis steht es?",
a:["Subsidiarität = Bund geht vor Ländern; Länder gehen vor Kommunen – vertikale Kompetenzverteilung im Föderalismus","Subsidiarität = Staatliche Hilfe tritt erst ein, wenn kleinere Einheiten (Individuum, Familie, Gemeinde, freie Träger) nicht ausreichen – das steht in Spannung zum universalistischen Sozialstaat, der umfassende Absicherung für alle garantiert","Subsidiarität = Vorrang privater Vorsorge vor staatlicher Absicherung in allen Bereichen der Sozialpolitik","Subsidiarität = Bundesrecht geht Landesrecht vor im Sozialversicherungsrecht"],
c:1,
e:"Subsidiaritätsprinzip (christliche Soziallehre, Encyclica Quadragesimo Anno 1931): Was die kleinere Einheit kann, soll ihr überlassen bleiben. Reihenfolge: Individuum → Familie → Nachbarschaft → Vereine/Kirchen → Gemeinde → Land → Bund. Spannungsverhältnis: Ein konsequenter Sozialstaat, der jedem ein würdiges Leben garantiert (BVerfG), muss manchmal einspringen, bevor kleinere Einheiten versagen."},

{cat:"sozialstaat",diff:"schwer",
q:"Was unterscheidet das 'Beveridge-Modell' vom 'Bismarck-Modell', und welche sozialen Gruppen begünstigt bzw. benachteiligt jedes Modell?",
a:["Beveridge = privat finanziert; Bismarck = staatlich finanziert – Beveridge bevorzugt Reiche, Bismarck schützt Arme","Beveridge = steuerfinanziert, universell, Pauschalleis­tungen; begünstigt Nichterwerbstätige, Frauen mit Erwerbsunterbrechungen; Bismarck = beitragsfinanziert, Leistungen an Beschäftigung geknüpft; begünstigt Vollzeiterwerbstätige, benachteiligt Teilzeitkräfte und Familienphasen","Beveridge = Skandinavisches Modell, Bismarck = US-amerikanisches Modell; beide haben ähnliche Leistungsprofile","Beveridge begünstigt Hochverdiener durch bessere private Ergänzungsversicherungen; Bismarck ist gleichheitsfördernd"],
c:1,
e:"Beveridge: universelle Grundsicherung unabhängig von Beschäftigung → begünstigt Frauen, Nicht-Erwerbstätige, atypisch Beschäftigte. Bismarck: Leistungen an Erwerbsarbeit geknüpft → bevorzugt Vollzeitbeschäftigte mit langer Versicherungsbiografie; benachteiligt Teilzeitarbeitende (oft Frauen), Solo-Selbstständige, Menschen mit Erwerbsunterbrechungen. Deutsche Reform-Debatte: universeller Anspruch vs. Bismarck-Logik."},

{cat:"sozialstaat",diff:"schwer",
q:"Was meint 'aktivierender Sozialstaat' (Schröder/Blair, 'Third Way'), und was war die verfassungsrechtliche Konsequenz?",
a:["Aktivierender Sozialstaat = mehr staatliche Aktivitäten zur Beschäftigungsförderung ohne Sanktionen – das BVerfG hat das vollständig bestätigt","Aktivierender Sozialstaat = 'Fördern und Fordern': Leistungen werden mit Verhaltensauflagen verknüpft – das BVerfG hat 2019 geurteilt, dass vollständige Leistungskürzungen bei Pflichtverletzung verfassungswidrig sind, weil sie das Existenzminimum tangieren","Aktivierender Sozialstaat = staatliche Beschäftigungsgarantie für alle Erwerbslosen, die sich aktiv bewerben","Das BVerfG hat den aktivierenden Sozialstaat generell als verfassungswidrig eingestuft"],
c:1,
e:"Hartz IV (2005): Leistungen an Bedingungen geknüpft (Bewerbungspflichten, Zumutbarkeit). BVerfG-Urteil November 2019: Totalsanktionen (vollständige Kürzung auf 0) sind verfassungswidrig, weil Art. 1 (Menschenwürde) + Art. 20 Abs. 1 GG ein unantastbares Existenzminimum schützen. Sanktionen bis 30% sind unter strengen Bedingungen zulässig. Bürgergeld (2023) reagierte auf dieses Urteil."},

{cat:"sozialstaat",diff:"leicht",
q:"Was ist das Bürgergeld (2023), und worin unterscheidet es sich in Philosophie und Ausgestaltung von Hartz IV?",
a:["Das Bürgergeld ist ein bedingungsloses Grundeinkommen für alle Bürger über 18","Das Bürgergeld ist die neue staatliche Grundsicherung für Erwerbslose – im Vergleich zu Hartz IV höherer Regelsatz, 6-monatige Vertrauenszeit, weniger harte Sanktionen, stärkerer Fokus auf Qualifizierung statt kurzfristiger Stellenvermittlung","Das Bürgergeld schafft alle Sanktionen ab und entspricht damit einem Recht auf staatliche Unterstützung ohne Gegenleistung","Das Bürgergeld ist ausschließlich für ältere Langzeitarbeitslose konzipiert und ersetzt teilweise die Rentenversicherung"],
c:1,
e:"Bürgergeld (Bürgergeldgesetz, 1.1.2023): Regelsatz 2024 = 563€ (Alleinstehende). Neuerungen: 6 Monate Vertrauenszeit (keine Sanktionen für Meldeversäumnisse), Vermögensschonung erhöht, Weiterbildungsprämien, stärkerer Fokus auf Qualifizierung. Sanktionen bleiben (bis 30%), vollständige Kürzungen verfassungswidrig (BVerfG 2019). Ziel: würdevollere Grundsicherung, mehr Nachhaltigkeit."},

{cat:"sozialstaat",diff:"mittel",
q:"Was ist Esping-Andersens 'Drei-Welten-Modell' des Wohlfahrtsstaats?",
a:["Eine Klassifikation von Sozialstaaten nach Ausgabenniveau: hoch (Skandinavien), mittel (Deutschland), niedrig (USA)","Drei Regime nach Dekommodifizierungsgrad und Stratifizierungseffekt: liberal (USA/UK – Markt dominant), konservativ-korporatistisch (DE/FR – Bismarck-Logik, Erwerbsarbeit) und sozialdemokratisch (Skandinavien – universell, hohe Dekommodifizierung)","Drei historische Phasen der Wohlfahrtsstaatsentwicklung: Entstehung, Ausbau, Krise","Ein Modell, das nach der Finanzierungsquelle (Steuern vs. Beiträge) Sozialstaaten in drei Typen einteilt"],
c:1,
e:"Esping-Andersen (1990): Liberal = Markt zuerst, residuale Staatshilfe (USA, UK). Konservativ-korporatistisch = Bismarck, an Erwerbsarbeit geknüpft, Familienprinzip (DE, FR, IT). Sozialdemokratisch = universell, dekommodifizierend, hohe Steuerfinanzierung (SE, DK, NO). Deutschland: konservativ, aber mit sozialdemokratischen Elementen. Kritik: vernachlässigt Geschlecht, Südeuropa."},

{cat:"sozialstaat",diff:"mittel",
q:"Was ist 'Dekommodifizierung', und wie misst Esping-Andersen damit die Qualität eines Sozialstaats?",
a:["Dekommodifizierung = staatliche Übernahme privater Unternehmen zur Daseinsvorsorge","Dekommodifizierung = das Ausmaß, in dem Bürger ihren Lebensunterhalt ohne Abhängigkeit vom Arbeitsmarkt bestreiten können – gemessen durch Zugangsvoraussetzungen, Leistungsniveau und Bezugsdauer von Sozialleistungen","Dekommodifizierung = die Entwertung von Waren durch staatliche Preisregulierung","Dekommodifizierung meint, dass Sozialleistungen nicht mehr an Arbeitsmarktbedingungen angepasst werden, was zum Rückzug aus dem Arbeitsmarkt führt"],
c:1,
e:"Dekommodifizierung (Esping-Andersen): Menschen werden von der Ware 'Arbeitskraft' emanzipiert. Hoch dekommodifiziert: man kann aufhören zu arbeiten, ohne sofort existenziell bedroht zu sein (gute ALG-Leistungen, lange Bezugsdauer, niedrige Schwellen). Gemessen durch drei Indizes: Renten-, Kranken-, Arbeitslosenversicherung. Hoch: Skandinavien. Niedrig: USA. Deutschland: mittel."},

{cat:"sozialstaat",diff:"schwer",
q:"Was meint die 'Armutsfalle', und welche Zuverdienstregelung versucht das Bürgergeld, sie zu entschärfen?",
a:["Armutsfalle = Menschen werden durch staatliche Kontrollen daran gehindert, aus der Armut aufzusteigen","Armutsfalle = Situation, in der Aufnahme oder Ausweitung von Erwerbsarbeit kaum zu mehr verfügbarem Einkommen führt, weil Sozialleistungen zeitgleich wegfallen und Steuern/Beiträge steigen – effektiver Grenzsteuersatz kann >80% sein; Bürgergeld: Freibeträge beim Zuverdienst sollen Anreize verbessern","Armutsfalle = dauerhafter Verbleib in Armut durch mangelnde Bildungsangebote, die der Sozialstaat nicht bereitstellt","Armutsfalle = Phänomen, bei dem Kinder armer Eltern statistisch häufiger selbst arm werden"],
c:1,
e:"Armutsfalle (poverty trap): Beim Übergang von Transferleistungen in Erwerbsarbeit werden Leistungen abrupt entzogen, Sozialversicherungsbeiträge und Steuern setzen ein → effektiver Grenzsteuersatz auf Mehrverdienst extrem hoch. Bürgergeld: gestaffelte Freibeträge. 100–520€ Bruttoverdienst: 20% Freibetrag. 520–1000€: 30% Freibetrag. Ziel: Arbeit lohnt sich mehr. Problem noch nicht vollständig gelöst."},

{cat:"sozialstaat",diff:"schwer",
q:"Wie hat das BVerfG das Recht auf ein Existenzminimum dogmatisch hergeleitet?",
a:["Aus Art. 20 Abs. 1 GG allein – das Sozialstaatsprinzip enthält implizit das Recht auf Grundversorgung","Aus Art. 1 Abs. 1 GG (Menschenwürde) in Verbindung mit dem Sozialstaatsprinzip (Art. 20 Abs. 1 GG) – der Staat ist verpflichtet, die materiellen Voraussetzungen für ein menschenwürdiges Dasein zu sichern, wobei das physische und soziokulturelle Existenzminimum gedeckt sein muss","Aus Art. 3 GG (Gleichheitsgrundsatz) – alle Bürger haben ein Recht auf gleiche materielle Versorgung","Aus Art. 14 GG (Eigentum) – das Eigentum an der eigenen Arbeitskraft begründet einen Anspruch auf Mindestentlohnung"],
c:1,
e:"BVerfG, 9. Februar 2010 (Hartz IV-Urteil): Das Grundrecht auf ein menschenwürdiges Existenzminimum leitet sich aus Art. 1 Abs. 1 GG (Menschenwürde ist unantastbar) in Verbindung mit Art. 20 Abs. 1 GG (Sozialstaatsprinzip) ab. Es umfasst ein physisches Existenzminimum (Nahrung, Kleidung, Unterkunft) und ein soziokulturelles Minimum (Teilhabe am gesellschaftlichen Leben). Regelleistungen müssen nachvollziehbar und transparent berechnet sein."},

{cat:"sozialstaat",diff:"leicht",
q:"Was sind die fünf Säulen der deutschen Sozialversicherung?",
a:["Kranken-, Renten-, Pflege-, Unfall- und Bildungsversicherung","Kranken-, Renten-, Pflege-, Unfall- und Arbeitslosenversicherung","Kranken-, Renten-, Arbeitslosen-, Grundsicherungs- und Pflegeversicherung","Kranken-, Renten-, Pflege-, Arbeitslosen- und Eigenheimversicherung"],
c:1,
e:"Die 5 Säulen der GKV: 1) Krankenversicherung (1883), 2) Unfallversicherung (1884), 3) Rentenversicherung (1889), 4) Arbeitslosenversicherung (1927), 5) Pflegeversicherung (1995). Alle sind Pflichtversicherungen mit Beitragsfinanzierung. Grundsicherung (Bürgergeld) ist keine Versicherung, sondern steuerfinanzierte Fürsorge."},

{cat:"sozialstaat",diff:"mittel",
q:"Was ist das 'Normalarbeitsverhältnis', und warum ist seine Erosion sozialpolitisch problematisch?",
a:["Normalarbeitsverhältnis = gesetzlich definierter Mindeststandard für alle Beschäftigungsformen; seine Erosion zeigt, dass der Gesetzgeber Schutzstandards abbaut","Normalarbeitsverhältnis = unbefristete Vollzeitstelle mit sozialversicherungspflichtiger Beschäftigung und Tarifvertrag; seine Erosion durch Leiharbeit, Minijobs, Befristung gefährdet lückenlose Versicherungsbiografien und führt zu niedrigen Renten und unzureichender Absicherung","Normalarbeitsverhältnis = Beschäftigung mit 40-Stunden-Woche; seine Erosion durch Teilzeit belastet die Volkswirtschaft","Normalarbeitsverhältnis war nur in der alten Bundesrepublik verbreitet und ist für Ostdeutschland historisch nicht relevant"],
c:1,
e:"Normalarbeitsverhältnis (NAV): unbefristet, Vollzeit, sozialversicherungspflichtig, oft tarifgebunden – Grundlage des Bismarck-Modells. Erosion seit 1990er Jahren: ca. 25% atypische Beschäftigung (Teilzeit, Leiharbeit, Befristung, Minijobs). Konsequenz: diskontinuierliche Versicherungsbiografien → niedrige Renten (Altersarmut wächst) → schlechtere ALG-I-Ansprüche. Sozialstaat, der an NAV hängt, verliert Schutzwirkung."},

{cat:"sozialstaat",diff:"schwer",
q:"Was meint das 'Solidaritätsprinzip' in der GKV konkret, und welches Spannungsverhältnis zur privaten Krankenversicherung entsteht daraus?",
a:["GKV-Solidarität = alle Versicherten zahlen denselben Prozentsatz, erhalten aber nach Bedarf unterschiedliche Leistungen","GKV-Solidarprinzip: Beitrag nach Einkommen, Leistung nach medizinischem Bedarf – Einkommensschwache, Chronischkranke, Familien werden quersubventioniert; PKV-Versicherte (tendenziell Gutverdiener und Gesunde) verlassen die Solidargemeinschaft, wodurch die GKV-Risikopools teurer werden","GKV und PKV haben dasselbe Solidarprinzip, da das SGB V für beide gilt","GKV-Solidarität = gleiche Leistungen für alle bei gleichem Beitragssatz – die PKV bietet nur Mehrleistungen obendrauf"],
c:1,
e:"GKV-Solidarprinzip: Gut­verdiener, Gesunde und kinderlose Mitglieder subventionieren Einkommensschwache, Kranke und beitragsfrei mitversicherte Familienmitglieder. Problem: Gutverdiener können in die PKV wechseln (ab bestimmtem Einkommen). Das entzieht der GKV Hochbeitragszahler und Gesunde → Risikostruktur der GKV verschlechtert sich → Beitragssätze steigen. Debatte: Bürgerversicherung (alle in GKV) vs. Status quo."},

/* ──────────────── ANALYSE & PRÜFUNG (20) ──────────────── */
{cat:"analyse",diff:"leicht",
q:"Was verlangt der Operator 'analysieren' im Hamburger PGW-Abitur genau, und wie unterscheidet er sich von 'beschreiben'?",
a:["'Analysieren' und 'beschreiben' sind synonyme Operatoren – beide fordern eine detaillierte Wiedergabe des Sachverhalts","'Beschreiben' = Was ist der Fall? (Wiedergabe von Merkmalen und Fakten); 'Analysieren' = Warum ist es so? Wie hängt es zusammen? (Strukturen, Ursachen, Wirkungen, Einordnung in Modelle und Fachbegriffe)","'Analysieren' = eigene Meinung und Bewertung einbringen, 'beschreiben' = neutral bleiben","'Analysieren' ist ein Operator für grundlegendes Niveau; 'beschreiben' ist anspruchsvoller und nur für erhöhtes Niveau"],
c:1,
e:"Häufiger Fehler: Statistiken nur beschreiben statt analysieren. Beschreibung: 'Laut Grafik verdienen Frauen weniger.' Analyse: 'Der Gender Pay Gap von 18% lässt sich auf Berufssegregation (Frauen in schlechter bezahlten Branchen), höhere Teilzeitquote und direkte Diskriminierung zurückführen. Bourdieus Habitus-Konzept erklärt, warum Frauen bestimmte Berufe wählen...' Analyse = Ursache-Wirkungs-Ketten + Modelleinordnung."},

{cat:"analyse",diff:"leicht",
q:"Was unterscheidet 'erörtern' von 'bewerten' als Operatoren?",
a:["'Erörtern' fordert eine eigene Meinung ohne Argumente; 'bewerten' fordert Argumente ohne Meinung","'Erörtern' = strukturierte Abwägung von Pro- und Contra-Argumenten zu einer These, abgeschlossen durch begründetes Fazit; 'bewerten' = begründetes eigenes Urteil auf Basis von Kriterien, direkter und positionsstärker als eine Erörterung","'Erörtern' ist ein Operator für Sachanalysen; 'bewerten' ist ein Operator für Gestaltungsaufgaben","Beide Operatoren fordern dasselbe – nur der formale Aufbau unterscheidet sich"],
c:1,
e:"Erörtern: 1) These vorstellen. 2) Pro-Argumente mit Belegen. 3) Contra-Argumente mit Belegen. 4) Abwägung. 5) Begründetes Fazit. Der Weg ist entscheidend. Bewerten: Direktere Positionierung zu einem Urteil, Kriterien benennen, Urteil begründen. Im erhöhten Niveau wird eigenständiges, theoriebezogenes Urteil erwartet, kein 'Einerseits-Andererseits' ohne Gewichtung."},

{cat:"analyse",diff:"mittel",
q:"Was ist der Unterschied zwischen 'Sachanalyse' und 'Bewertung' in der Aufgabenstruktur des Hamburger PGW-Abiturs, und warum ist die Trennung wichtig?",
a:["Sachanalyse = qualitative Analyse; Bewertung = quantitative Auswertung von Statistiken","Sachanalyse = neutrale Darstellung von Fakten, Modellen, Positionen ohne eigenes Werturteil; Bewertung = begründetes eigenes Urteil – die Trennung ist wichtig, weil eigene Wertungen in der Sachanalyse als Fehler gewertet werden","Beide Teile sind im Hamburger Abitur identisch strukturiert – die Unterscheidung ist formaler Natur","Sachanalyse ist der schwierigere Teil, weil er tiefes Fachwissen verlangt; Bewertung ist einfacher, weil jede begründete Meinung akzeptiert wird"],
c:1,
e:"Hamburger Abitur PGW: Typische Aufgabenstruktur – Teilaufgabe 1: 'Erläutern Sie...' oder 'Stellen Sie dar...' = Sachanalyse (neutral, modellgestützt). Teilaufgabe 2: 'Analysieren Sie...' = Anwendung auf Material. Teilaufgabe 3: 'Erörtern Sie...' oder 'Nehmen Sie Stellung...' = Bewertung. Eigene Wertungen in der Sachanalyse = Formfehler. In der Bewertung fehlendes Urteil = Formfehler."},

{cat:"analyse",diff:"mittel",
q:"Wie wird ein Sozialstrukturmodell methodisch korrekt auf ein Fallbeispiel angewendet?",
a:["Man nennt den Modellnamen und erklärt kurz, warum es passt – das ist ausreichend für die Anwendung","Vier Schritte: 1) Modell mit Kernbegriffen vorstellen. 2) Relevante Merkmale des Falls aus dem Material herausarbeiten. 3) Merkmale den Modellkategorien zuordnen und Verbindung explizit begründen. 4) Aussagekraft und Grenzen des Modells für diesen Fall kritisch reflektieren","Man erklärt das Modell vollständig aus dem Gedächtnis und erwähnt danach das Fallbeispiel kurz","Man sucht im Fallbeispiel nach wörtlichen Entsprechungen zu Modellbegriffen und listet sie auf"],
c:1,
e:"Modellanwendung – häufige Fehler: 1) Modell ausführlich erklären, Fallbeispiel aber kaum erwähnen. 2) Fallbeispiel beschreiben, Modell aber nicht anwenden. 3) Anwendung ohne kritische Reflexion ('Grenzen des Modells'). Richtig: Schritte 1–4 explizit vollziehen. Bsp.: 'Bourdieus Habitusbegriff (Schritt 1) erklärt die Aussage der Figur X (Schritt 2), weil ihr Sprachstil inkorporiertes kulturelles Kapital zeigt (Schritt 3). Das Modell vernachlässigt allerdings... (Schritt 4).'"},

{cat:"analyse",diff:"schwer",
q:"Was ist bei einer Gestaltungsaufgabe im Hamburger PGW-Abitur besonders zu beachten, und welche typischen Fehler werden gemacht?",
a:["Gestaltungsaufgaben erfordern keine Fachkenntnisse – es zählen Kreativität und sprachliche Qualität","Genretreue (Rede: direkte Ansprache, Appelle, Wir-Perspektive; Kommentar: argumentativ, klare Position; Leserbrief: persönlich, konkreter Anlass), adressatengerechte Sprache, eingebettetes Fachwissen – Fehler: Referat schreiben statt Genre einhalten, oder Position vermeiden","Gestaltungsaufgaben sind leichter als Erörterungsaufgaben, weil keine Modellkenntnisse erforderlich sind","Gestaltungsaufgaben sollten neutral gehalten sein, um alle Positionen gleich zu behandeln"],
c:1,
e:"Gestaltungsaufgabe (Hamburg): 1) Genre einhalten: Rede = Publikum direkt ansprechen, 'Sehr geehrte Damen und Herren', Schlussappell. Kommentar = journalistischer Duktus, klare These, keine 'Einerseits-Andererseits'. 2) Klare Position = anders als bei Erörterung. 3) Fachinhalt einbetten: Bourdieu nennen, nicht als Fachaufsatz zitieren. 4) Typische Fehler: allgemeines Referat schreiben, keine Genremerkmale aufweisen, keine eigene Position."},

{cat:"analyse",diff:"mittel",
q:"Was meint 'Transfer' als Kompetenzstufe im Hamburger PGW-Abitur?",
a:["Übertragung von Textstellen aus dem Unterrichtsmaterial in die Klausur durch präzises Zitieren","Die Fähigkeit, im Unterricht erworbene Konzepte und Modelle auf neue, unbekannte Fälle oder Materialien anzuwenden – nicht nur Reproduktion, sondern produktive Nutzung von Wissen","Verwendung von Transfermethoden aus anderen Fächern (z.B. Mathematik) in PGW-Klausuren","Übertragung der Aufgabenstellung in eigene Worte als Vorbereitung für die Beantwortung"],
c:1,
e:"Transfer = höchste Kompetenzstufe. Im Unterricht: Bourdieu an Bildungsungleichheit gelernt. In Klausur: neues Material zu Wohnungsmarkt → Habitus und kulturelles Kapital auf Wohnraumzugang anwenden. Transfer zeigt: Konzept verstanden, nicht nur memoriert. Prüfungsaufgaben im Hamburger Abitur sind so konstruiert, dass bekannte Theorien auf unbekannte Fälle angewendet werden müssen."},

{cat:"analyse",diff:"schwer",
q:"Wie vermeidet man 'Scheinargumente' in einer Abitur-Erörterung, und welche Typen kommen besonders häufig vor?",
a:["Scheinargumente vermeidet man, indem man nur Argumente aus dem Unterricht verwendet und keine eigenen entwickelt","Scheinargumente entstehen durch logische Fehlschlüsse: Strohmann (Gegenposition verzerrt darstellen), Ad Hominem (Person statt Argument angreifen), Petitio Principii (These als Begründung für sich selbst), falsche Dichotomie (nur zwei Optionen, obwohl es mehr gibt) – man vermeidet sie durch faire Darstellung der Gegenposition und empirische Belege","Scheinargumente sind in der Prüfung erlaubt, wenn sie überzeugend formuliert sind","Scheinargumente entstehen nur, wenn man zu wenig Fachwissen hat – mit ausreichendem Wissen entstehen sie automatisch nicht"],
c:1,
e:"Häufige Scheinargumente in PGW: 1) Strohmann: 'Wer für den Sozialstaat ist, will den Kommunismus' – Gegenposition verzerrt. 2) Petitio Principii: 'Umverteilung ist gerecht, weil sie gerecht verteilt' – These als Begründung. 3) Appell an Mehrheit: 'Die meisten Menschen wollen X' ≠ Argument für X. 4) Falsche Dichotomie: 'Entweder Marktwirtschaft oder Sozialstaat' – Mischformen ignoriert. Gutes Gegenargument = stark formulieren, dann entkräften."},

{cat:"analyse",diff:"leicht",
q:"Wie viele Aufgaben werden im Hamburger PGW-Abitur vorgelegt, und welche Auswahlregel gilt?",
a:["2 Aufgaben, beide müssen vollständig bearbeitet werden","3 Aufgaben aus 2 verschiedenen Schwerpunkten werden vorgelegt – der Prüfling wählt eine aus und bearbeitet diese vollständig","4 Aufgaben, davon 2 Pflicht und 2 Wahlaufgaben nach freier Entscheidung","3 Aufgaben werden vorgelegt, der Prüfling bearbeitet 2 nach eigener Wahl"],
c:1,
e:"Hamburger Abitur PGW 2026: 3 Aufgaben (I, II, III) aus 2 verschiedenen Schwerpunkten. Prüfling: erhält alle 3, prüft zu Beginn die Vollständigkeit (Anzahl Blätter, Anlagen), wählt dann eine aus und bearbeitet diese vollständig. Auf der Reinschrift muss die Aufgabennummer vermerkt werden. Keine gesonderte Lese- oder Auswahlzeit. Bearbeitungszeit: 255 Min (Grundniveau) / 315 Min (erhöhtes Niveau)."},

{cat:"analyse",diff:"mittel",
q:"Was sind die erlaubten Hilfsmittel im Hamburger PGW-Abitur 2026?",
a:["Grundgesetz, Rechtschreibwörterbuch und eigene Zusammenfassungen aus dem Unterricht","Grundgesetz für die Bundesrepublik Deutschland sowie Rechtschreibwörterbuch und/oder Fremdwörterlexikon","Taschenrechner, Wörterbuch und Grundgesetz mit eigenen Randnotizen","Grundgesetz, Wirtschaftslexikon und ein zweisprachiges Wörterbuch bei Schülern mit Migrationshintergrund"],
c:1,
e:"Hamburger Abitur PGW: Erlaubte Hilfsmittel = Grundgesetz für die BRD (ohne Kommentare und eigene Eintragungen) + Rechtschreibwörterbuch / Fremdwörterlexikon. Kein Taschenrechner, keine eigenen Mitschriften, kein annotiertes GG. Das GG ist besonders wichtig für Art. 1 (Menschenwürde), Art. 3 (Gleichheit), Art. 14 (Eigentum/Sozialbindung), Art. 20 (Sozialstaatsprinzip), Art. 28 (Sozialstaatsprinzip Länder)."},

{cat:"analyse",diff:"schwer",
q:"Was meint 'Multiperspektivität' als Kompetenzziel im Hamburger Rahmenplan PGW, und wie wird sie in einer Erörterung operationalisiert?",
a:["Multiperspektivität = mehrere Quellen auswerten; operationalisiert durch Zitieren von mindestens drei verschiedenen Autoren","Multiperspektivität = denselben Sachverhalt durch verschiedene theoretische Linsen, politische Positionen und Akteursebenen analysieren; operationalisiert durch expliziten Perspektivwechsel: 'Aus liberaler Sicht... Aus egalitaristischer Sicht... Aus der Perspektive von Bourdieu...'","Multiperspektivität = ausgewogene Darstellung aller Meinungen ohne eigenes Urteil; das Fazit bleibt offen","Multiperspektivität = Berücksichtigung internationaler Beispiele neben deutschen Sachverhalten"],
c:1,
e:"Hamburger Rahmenplan PGW: Multiperspektivität als Kernanforderung. Operationalisierung in Klausur: 1) Theoretische Perspektive: 'Funktionalismus erklärt X als..., Konflikttheorie sieht X als...' 2) Politische Perspektive: 'Aus liberaler Sicht ist X legitim, weil...; aus egalitaristischer Sicht ist X ungerecht, weil...' 3) Akteursebene: individuell, institutionell, gesellschaftlich. Multiperspektivität ≠ Meinungslosigkeit; am Ende steht ein begründetes, eigenständiges Urteil."},

{cat:"analyse",diff:"mittel",
q:"Was unterscheidet eine 'Erörterungsaufgabe' von einer 'Gestaltungsaufgabe' im Hamburger PGW-Abitur?",
a:["Erörterungsaufgaben sind schwieriger; Gestaltungsaufgaben werden schwächeren Schülern empfohlen","Erörterungsaufgabe = Sachanalyse + argumentative Auseinandersetzung mit einer These im wissenschaftlich-analytischen Stil; Gestaltungsaufgabe = produktorientiert mit bestimmter Textsorte (Rede, Kommentar, Flyer), klarer Position, genrespezifischer Form und gleichem Fachgehaltsanspruch","Gestaltungsaufgaben erfordern keine Fachkenntnisse, nur sprachliche Kompetenz","Es gibt im Hamburger Abitur keine Gestaltungsaufgaben – nur Erörterungen"],
c:1,
e:"Hamburger Abitur PGW: Von 3 Aufgaben sind 2 Erörterungsaufgaben, 1 Gestaltungsaufgabe (oder eine Aufgabe mit gestalterischen Elementen). Erörterung: analytisch-wissenschaftlicher Stil, abwägend. Gestaltung: Textsorte genau einhalten (Rede, Kommentar, Leserbrief, Flugblatt), klare Position einnehmen, Fachinhalt einbetten. Fachgehalt und Anspruchsniveau sind bei beiden gleich hoch."},

{cat:"analyse",diff:"schwer",
q:"Was sind die typischen Qualitätsmerkmale einer sehr guten (15 Punkte) Abiturklausur im Fach PGW auf erhöhtem Niveau?",
a:["Sehr lange Ausführungen mit vielen Zitaten aus dem Unterrichtsmaterial und einer neutralen Schlussposition","Präzise Verwendung von Fachbegriffen, Anwendung relevanter Theorien und Modelle auf das spezifische Material, begründetes eigenständiges Urteil, klare Struktur, empirische Belege, kritische Reflexion der Modellgrenzen und Perspektivwechsel","Kreative Sprache und viele Beispiele aus dem Alltag als Ersatz für Fachbegriffe","Vollständige Wiedergabe aller im Unterricht behandelten Theorien, auch wenn sie für die Aufgabe nicht relevant sind"],
c:1,
e:"15-Punkte-Klausur PGW: 1) Fachbegriffe korrekt und kontextuell eingesetzt (nicht aufgezählt). 2) Theorieanwendung: Modell auf spezifischen Fall angewendet, nicht nur erklärt. 3) Eigenständiges Urteil: keine 'Einerseits-Andererseits'-Schleife, sondern begründete Position. 4) Empirische Belege: Gini, PISA, GPG etc. 5) Modellkritik: Grenzen des verwendeten Modells benennen. 6) Genrekonformität (bei Gestaltungsaufgaben). 7) Roter Faden und Stringenz."},

{cat:"analyse",diff:"leicht",
q:"Was ist der Unterschied zwischen 'These' und 'Argument' in einer PGW-Erörterung?",
a:["These ist kürzer als ein Argument; beide belegen dieselbe Behauptung","These = behauptete Position (Hauptbehauptung, die begründet werden muss); Argument = Begründung für oder gegen die These, bestehend aus Behauptung + Begründung + empirischem Beleg","Argument ist eine spezifische These; These ist ein allgemeines Argument","In PGW-Klausuren gibt es keine Thesen – nur Fragestellungen, auf die Argumente folgen"],
c:1,
e:"Erörterungsstruktur: These (Hauptbehauptung, z.B. 'Der Sozialstaat ist notwendig zur Bekämpfung sozialer Ungleichheit') → Argumente = Behauptung + Begründung + Beleg + ggf. Beispiel. Stärke eines Arguments = Belastbarkeit des Belegs + Logik der Begründung. Im erhöhten Niveau: Argumente müssen theoriebezogen und empirisch gestützt sein, nicht nur plausibel klingen."},

{cat:"analyse",diff:"mittel",
q:"Warum reicht es nicht, in einer PGW-Klausur nur Fachbegriffe zu nennen, ohne sie anzuwenden?",
a:["Fachbegriffe werden im Abitur nicht bewertet – nur Argumentation und Sprache zählen","Fachbegriffe signalisieren Wissen, zeigen aber nur dann Kompetenz, wenn sie korrekt und kontextuell eingesetzt werden – ein Fachbegriff im richtigen Kontext zeigt Verständnis; eine Aufzählung zeigt nur Memorieren ohne Anwendungsverständnis","Fachbegriffe aus anderen Fächern können Fachbegriffe aus PGW ersetzen, wenn sie inhaltlich passen","Zu viele Fachbegriffe führen zu Punktabzug, weil sie den Text unlesbar machen"],
c:1,
e:"Typischer Fehler: 'In der Gesellschaft gibt es Habitus, Kapital, Milieus und Schichten.' ← Aufzählung ohne Anwendung. Richtig: 'Der Habitus von Familie X, geprägt durch ihren restringierten Sprachkode und das Fehlen inkorporierten kulturellen Kapitals, erklärt die niedrige Schulempfehlung des Kindes besser als individuelle Leistungsmängel.' ← Fachbegriff korrekt im Kontext, zeigt echtes Verständnis."},

{cat:"analyse",diff:"schwer",
q:"Wie geht man methodisch mit widersprüchlichen Materialien in einer PGW-Aufgabe um?",
a:["Man wählt das Material, das die eigene These am besten stützt, und ignoriert widersprechendes Material","Man stellt beide Positionen korrekt dar, analysiert den Widerspruch (unterschiedliche Theorien? Interessen? empirische Daten?), entwickelt Kriterien für die Beurteilung und formuliert ein begründetes Fazit – kein 'beide haben recht'","Man fasst alle Materialien zusammen und weist darauf hin, dass Sozialwissenschaft keine eindeutigen Antworten liefert","Man verwendet nur das Material, das von der Lehrkraft im Unterricht als 'richtig' eingestuft wurde"],
c:1,
e:"Widersprüchliche Materialien = typische Aufgabenstellung im Hamburger Abitur erhöhtes Niveau. Vorgehen: 1) Beide Positionen fair und kompetent darstellen (kein Strohmann). 2) Widerspruch explizit benennen: Empirisch? Theoretisch? Interessengeleitet? 3) Bewertungskriterien entwickeln: Erklärungsgehalt des Modells? Repräsentativität der Daten? 4) Begründetes Urteil – trotz Widerspruch. Keine Ausweichlösung: 'Es ist kompliziert.'"}

]; // Ende Fragenkatalog

const META={
  modelle:      {name:"Sozialstrukturmodelle",  dot:"#a78bfa",bg:"rgba(167,139,250,.12)",c:"#c4b5fd"},
  begriffe:     {name:"Fachbegriffe",            dot:"#34d399",bg:"rgba(52,211,153,.12)", c:"#6ee7b7"},
  gerechtigkeit:{name:"Gerechtigkeitstheorien",  dot:"#fbbf24",bg:"rgba(251,191,36,.12)",c:"#fde68a"},
  sozialstaat:  {name:"Sozialstaat",              dot:"#f472b6",bg:"rgba(244,114,182,.12)",c:"#f9a8d4"},
  analyse:      {name:"Analyse & Prüfung",        dot:"#60a5fa",bg:"rgba(96,165,250,.12)", c:"#93c5fd"}
};
const DL={leicht:"Leicht",mittel:"Mittel",schwer:"Schwer"};

let qs=[],idx=0,cor=0,wrg=0,cs={},selCat="all",selDiff="all";

function shuf(a){for(let i=a.length-1;i>0;i--){const j=Math.floor(Math.random()*(i+1));[a[i],a[j]]=[a[j],a[i]]}return a}
function pool(){return Q.filter(q=>(selCat==="all"||q.cat===selCat)&&(selDiff==="all"||q.diff===selDiff))}

function updateCounts(){
  document.getElementById("c-all").textContent=Q.length+" Fragen";
  Object.keys(META).forEach(k=>{
    document.getElementById("c-"+k).textContent=Q.filter(q=>q.cat===k).length+" Fragen";
  });
  document.getElementById("tc").textContent=pool().length;
}

document.querySelectorAll(".cc").forEach(c=>{
  c.onclick=()=>{
    document.querySelectorAll(".cc").forEach(x=>x.classList.remove("active"));
    c.classList.add("active");selCat=c.dataset.cat;
    document.getElementById("tc").textContent=pool().length;
  };
});
document.querySelectorAll(".db").forEach(b=>{
  b.onclick=()=>{
    document.querySelectorAll(".db").forEach(x=>x.classList.remove("active"));
    b.classList.add("active");selDiff=b.dataset.diff;
    document.getElementById("tc").textContent=pool().length;
  };
});

function showS(id){document.querySelectorAll(".screen").forEach(s=>s.classList.remove("active"));document.getElementById(id).classList.add("active")}

function startGame(){
  const p=pool();if(!p.length){alert("Keine Fragen für diese Auswahl.");return;}
  qs=shuf([...p]);idx=0;cor=0;wrg=0;cs={};
  showS("s1");render();
}

function render(){
  if(idx>=qs.length){result();return;}
  const q=qs[idx];
  document.getElementById("pf").style.width=Math.round((idx/qs.length)*100)+"%";
  document.getElementById("qctr").textContent="Frage "+(idx+1)+" / "+qs.length;
  document.getElementById("spill").textContent=cor+" richtig";
  const m=META[q.cat];
  const cp=document.getElementById("cpill");cp.textContent=m.name;cp.style.background=m.bg;cp.style.color=m.c;
  const dp=document.getElementById("dpill");dp.textContent=DL[q.diff];dp.className="dpill d"+q.diff[0];
  document.getElementById("qtxt").textContent=q.q;
  document.getElementById("expl").innerHTML="";
  document.getElementById("nxt").style.display="none";
  const sh=q.a.map((t,i)=>({t,i}));shuf(sh);
  const con=document.getElementById("ans");con.innerHTML="";
  sh.forEach(({t,i})=>{
    const b=document.createElement("button");b.className="ab";b.textContent=t;
    b.onclick=()=>ans(i===q.c,q,con,b);con.appendChild(b);
  });
}

function ans(ok,q,con,clicked){
  if(!cs[q.cat])cs[q.cat]={c:0,t:0};
  cs[q.cat].t++;
  con.querySelectorAll(".ab").forEach(b=>b.classList.add("dis"));
  if(ok){cor++;cs[q.cat].c++;clicked.classList.add("ok");}
  else{wrg++;clicked.classList.add("no");
    con.querySelectorAll(".ab").forEach(b=>{if(b.textContent===q.a[q.c])b.classList.add("rv");});
  }
  document.getElementById("expl").innerHTML='<div class="expl">'+q.e+'</div>';
  document.getElementById("nxt").style.display="block";
}
function next(){idx++;render();}

function result(){
  showS("s2");
  const tot=cor+wrg,pct=tot>0?Math.round((cor/tot)*100):0;
  document.getElementById("rc").textContent=cor;
  document.getElementById("rw").textContent=wrg;
  document.getElementById("rp").textContent=pct+"%";
  let g,msg,col;
  if(pct>=90){g="A+";msg="Hervorragend – bestens vorbereitet!";col="#34d399";}
  else if(pct>=75){g="B";msg="Solide – noch ein paar Lücken schließen.";col="#a78bfa";}
  else if(pct>=55){g="C";msg="Weiter üben – du bist auf dem richtigen Weg!";col="#fbbf24";}
  else{g="D";msg="Nochmal von vorne – du schaffst das!";col="#f87171";}
  document.getElementById("rg").textContent=g;
  document.getElementById("rg").style.color=col;
  document.getElementById("rm").textContent=msg;
  const div=document.getElementById("catres");div.innerHTML="";
  Object.entries(cs).forEach(([cat,{c,t}])=>{
    const p=Math.round((c/t)*100),m=META[cat];
    div.innerHTML+=`<div class="crr"><div class="crn">${m.name}</div><div class="cbt"><div class="cbf" style="width:${p}%;background:${m.dot}"></div></div><div class="crp">${p}%</div></div>`;
  });
}
updateCounts();
</script>
</body>
</html>
