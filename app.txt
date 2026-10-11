const goals = [
"kontroli impulsów i ich hamowania",
"koncentracji uwagi",
"tolerancji na stres i frustrację",
"komunikacji werbalnej i niewerbalnej",
"umiejętności organizacji, porządkowania i planowania",
"zachowań społecznych",
"integracji z grupą",
"integracji „ja” realnego z „ja” idealnym",
"umiejętności komunikacyjnych",
"relacji i więzi",
"wzrostu akceptacji i samooceny",
"motoryki małej i dużej",
"orientacji w rzeczywistości — co do czasu i miejsca",
"relacji międzyludzkich",
"wzrostu samoakceptacji i samooceny",
"jakości snu",
"wzbogacania metod diagnostycznych",
"koordynacji psychicznej",
"wzrostu pozytywnego nastawienia do życia",
"prawidłowego rozwoju",
"rozwoju umiejętności szkolnych",
"kształtowania tożsamości",
"ekspresji emocjonalnej",
"integracji w zakresie emocji i zachowania",
"osiągnięcia świadomości siebie",
"rozwoju samoświadomości emocjonalnej",
"umiejętności współpracy",
"relaksacji",
"aktywizacji",
"wzrostu spontanicznej kreatywności",
"usprawniania pamięci",
"wywoływania wspomnień",
"reminiscencji",
"uwagi i koncentracji na zadaniu",
"samoświadomości i pozytywnej samooceny",
"ćwiczeń fizycznych",
"rozwijania zainteresowań",
"dowartościowania emocjonalnego",
"wzmacniania prawidłowych nastawień i postaw",
"wdrażania do odpowiedzialności",
"funkcji percepcyjno-motorycznych",
"rehabilitacji",
"procesu leczenia",
"strategii relaksacyjnych",
"rozładowania napięć w sposób akceptowalny społecznie",
"umiejętności wychodzenia z inicjatywą",
"umiejętności rozpoznawania emocji i zachowań emocjonalnych",
"umiejętności planowania rozwiązywania problemów",
"decydowania i dokonywania wyborów",
"umiejętności budowania pogłębionych relacji opartych na wzajemności",
"poczucia bezpieczeństwa",
"poczucia kontroli, wpływu, sprawności i odpowiedzialności",
"właściwego poczucia własnej wartości",
"empatii i wrażliwości",
"zaangażowania w działaniu grupy",
"umiejętności przestrzegania reguł",
"troski o innych",
"zainteresowań prowadzących do akceptowalnej formy spędzania czasu wolnego",
"wiedzy dotyczącej zagrożeń społecznych, takich jak uzależnienia i przemoc, oraz możliwości reagowania",
"umiejętności rozpoznawania emocji",
"budowania relacji w grupie",
"rozwijania poczucia rytmu",
"prawidłowej reakcji na zmianę tempa, dynamiki i rejestru głosu",
"wyrabiania poczucia świadomego ruchu — rozluźnienia i napięcia ciała",
"inwencji twórczej i improwizacji ruchowej",
"rozpoznawania barwy dźwięków instrumentów, np. perkusyjnych",
"wzbudzania pożądanych emocji — uczuć, stanów afektywnych i nastrojów — oraz sterowania nimi",
"uwrażliwienia na muzykę i przyrodę",
"napięcia fizycznego i psychicznego",
"poziomu agresji",
"niepokoju i lęku",
"ograniczania niepożądanych zachowań i wzmacniania zachowań właściwych",
"stanu pobudzenia psychomotorycznego",
"napięcia emocjonalnego i mięśniowego",
"ujawniania i rozładowywania zablokowanych emocji i napięć",
"nowych wzorców zachowań",
"utrzymania relacji",
"socjalizacji",
"koordynacji ruchowej",
"koordynacji werbalno-ruchowej",
"koordynacji wzrokowo-ruchowej",
"uważnego słuchania i prawidłowej reakcji na polecenia",
"umiejętności gospodarowania oddechem",
"świadomego wyrażania emocji i rozpoznawania ich u innych",
"przyjemnego spędzania wolnego czasu",
"rozwoju osobowości pacjenta, seniora lub mieszkańca, głównie poprzez doznania estetyczne",
"wyrabiania u pacjentów lub seniorów postawy twórczej",
"wzbogacania zasobu doświadczeń emocjonalnych i intelektualnych",
"strategii postępowania",
"depresji"
];

const stages = [
["Uruchomienie","Pobudzenie, energia, gotowość do działania","stage-red"],
["Odreagowanie","Wyrażenie emocji, rozładowanie napięcia","stage-orange"],
["Zrytmizowanie","Rytm, koordynacja, współpraca","stage-yellow"],
["Uwrażliwienie","Słuchanie, emocje, wyobraźnia","stage-green"],
["Relaksacja","Wyciszenie, spokój, oddech","stage-teal"],
["Aktywizacja","Zaangażowanie, poczucie sprawczości","stage-blue"],
["Zakończenie","Podsumowanie, pozytywne emocje, pożegnanie","stage-pink"]
];

const appEl = document.getElementById("app");

function wrap(content, bg="mauve", back=false){
  appEl.innerHTML = `
    <section class="screen content ${bg}">
      ${back ? '<button class="back" onclick="history.back()">← Wróć</button>' : ""}
      ${content}
    </section>`;
  window.scrollTo(0,0);
}

function tile(title, subtitle, icon, go){
  return `<button class="tile" onclick="${go}"><div>${title}<br><small>${subtitle}</small></div><span>${icon}</span></button>`;
}

function home(){
  wrap(`
    <div class="logo-card">Muzyczny Medyk</div>
    <div class="subtitle">Terapia • Muzyka • Troska</div>
    <div class="tiles home-tiles">
      ${tile("Terapia zajęciowa","Teoria • Cele • Pomysły","🧩","go('tz')")}
      ${tile("MRM","Mobilna Rekreacja Muzyczna","🎵","go('mrm')")}
      ${tile("Zajęcia MRM","Gotowe scenariusze","📋","go('zajecia')")}
      ${tile("Granie w pokojach","Muzyka blisko mieszkańców","🎻","go('pokoje')")}
    </div>
    <div class="install-tip">Możesz dodać tę aplikację do ekranu głównego telefonu lub tabletu.</div>
  `, "blue");
}

function tz(){
  wrap(`
    <div class="title-card">Terapia zajęciowa</div>
    <div class="tiles">
      ${tile("BAZA CELÓW","90 celów terapeutycznych","🎯","go('goalsIntro')")}
      ${tile("Teoria TZ","Najważniejsze podstawy","📘","go('theory')")}
      ${tile("Pomysły","Inspiracje do zajęć","💡","go('ideas')")}
    </div>
  `, "green", true);
}

function goalsIntro(){
  wrap(`
    <div class="title-card">BAZA CELÓW</div>
    <div class="panel">
      <h2>Jak konstruować cele w TZ?</h2>
      <div class="goals-scheme">
        <table>
          <tr><th>1. Kierunek</th><th>2. Obszar</th><th>3. Działanie</th><th>4. Efekt</th></tr>
          <tr><td class="r1">ROZWIJANIE<br>WZMACNIANIE</td><td class="r2">emocji<br>relacji<br>sprawności</td><td class="r3">ćwiczenie<br>wspieranie<br>doskonalenie</td><td class="r4">większa samodzielność<br>lepsza komunikacja</td></tr>
          <tr><td class="r1">WSPOMAGANIE<br>WZBOGACANIE<br>POMNAŻANIE</td><td class="r2">zainteresowań<br>doświadczeń</td><td class="r3">aktywizowanie<br>motywowanie</td><td class="r4">większe zaangażowanie<br>lepszy nastrój</td></tr>
          <tr><td class="r1">OBNIŻANIE<br>REDUKOWANIE</td><td class="r2">napięcia<br>lęku<br>agresji</td><td class="r3">relaksowanie<br>wyciszanie</td><td class="r4">spokój<br>poczucie bezpieczeństwa</td></tr>
        </table>
      </div>
      <p><b>Przykłady:</b> rozwijanie koncentracji uwagi, wzmacnianie poczucia własnej wartości, obniżanie napięcia emocjonalnego.</p>
      <button class="tile small" onclick="goalPage(0)">Przejdź do celów 1–10 <span>→</span></button>
      <div class="page-no">1/10</div>
    </div>
  `, "teal", true);
}

function goalPage(p){
  const start = p*10;
  const items = goals.slice(start,start+10).map((g,i)=>{
    const n=start+i+1;
    return `<div class="goal-row c${i%6}"><div class="goal-num">${n}</div><div class="goal-text">… ${g}</div></div>`;
  }).join("");
  const prev = p>0 ? `<button class="back" onclick="goalPage(${p-1})">← Poprzednia</button>` : `<button class="back" onclick="go('goalsIntro')">← Tabelka</button>`;
  const next = p<8 ? `<button class="back" onclick="goalPage(${p+1})">Następna →</button>` : "";
  wrap(`
    <div class="title-card">BAZA CELÓW</div>
    <div class="panel goals-list">
      ${items}
      <div style="display:flex;justify-content:space-between;gap:10px;margin-top:18px">${prev}${next}</div>
      <div class="page-no">${p+2}/10</div>
    </div>
  `, "teal", true);
}

function mrm(){
  wrap(`
    <div class="title-card">MRM</div>
    <div class="subtitle">Mobilna Rekreacja Muzyczna</div>
    <div class="group-card">
      <h2>7 etapów MRM</h2>
      ${stages.map((s,i)=>`<button class="menu-item ${s[2]}" onclick="stage(${i})"><span><b>${i+1}. ${s[0]}</b><br><small>${s[1]}</small></span><span>›</span></button>`).join("")}
    </div>
  `, "mauve", true);
}

function stage(i){
  const s=stages[i];
  const tips = [
    ["Krótki ruch przy muzyce","Proste ćwiczenia pobudzające","Powitanie rytmem"],
    ["Swobodny ruch","Gra na instrumentach","Wyrażanie emocji dźwiękiem"],
    ["Klaskanie i tupanie","Proste rytmy","Bum Bum Rurki"],
    ["Słuchanie i nazywanie emocji","Muzyczne obrazy","Dialog muzyczny"],
    ["Ćwiczenia oddechowe","Spokojna muzyka","Rozluźnianie ciała"],
    ["Ruch do energicznej muzyki","Proste zadania w parach","Improwizacja"],
    ["Krótka rozmowa","Pożegnalny motyw muzyczny","Podsumowanie nastroju"]
  ][i];
  wrap(`
    <div class="title-card">${i+1}. ${s[0]}</div>
    <div class="panel ${s[2]}">
      <span class="tag">${s[1]}</span>
      <h2>Po co ten etap?</h2>
      <p>Etap pomaga dopasować poziom pobudzenia, emocji i aktywności do potrzeb uczestników oraz przygotować grupę do kolejnej części zajęć.</p>
      <h2>Propozycje ćwiczeń</h2>
      <ul>${tips.map(x=>`<li>${x}</li>`).join("")}</ul>
    </div>
  `, "green", true);
}

function theory(){
  wrap(`
    <div class="title-card">Teoria terapii zajęciowej</div>
    <div class="panel">
      <h2>Czym jest terapia zajęciowa?</h2>
      <p>To celowe wykorzystywanie aktywności, zajęć i codziennych działań do wspierania sprawności, samodzielności, relacji, emocji i jakości życia.</p>
      <h2>Główne założenie</h2>
      <p>Zajęcie ma znaczenie wtedy, gdy jest dobrane do możliwości, potrzeb i zainteresowań konkretnej osoby.</p>
    </div>
  `, "green", true);
}

function ideas(){
  wrap(`
    <div class="title-card">Pomysły na zajęcia</div>
    <div class="tiles">
      ${["Muzykoterapia","Trening pamięci","Zajęcia ruchowe","Arteterapia","Reminiscencja","Zajęcia sensoryczne"].map((x,i)=>tile(x,"Pomysł do wykorzystania",["🎵","🧠","🤸","🎨","🕰️","🌿"][i],"alert('Ten moduł będziemy rozwijać.')")).join("")}
    </div>
  `, "green", true);
}

function zajecia(){
  wrap(`
    <div class="title-card">Zajęcia MRM</div>
    <div class="panel">
      <h2>Gotowy schemat</h2>
      <p>1. Powitanie i uruchomienie</p>
      <p>2. Odreagowanie</p>
      <p>3. Zrytmizowanie</p>
      <p>4. Uwrażliwienie</p>
      <p>5. Relaksacja</p>
      <p>6. Aktywizacja</p>
      <p>7. Zakończenie</p>
    </div>
  `, "blue", true);
}

function pokoje(){
  wrap(`
    <div class="title-card">Granie w pokojach</div>
    <div class="panel">
      <h2>Muzyka blisko mieszkańców</h2>
      <p>Wybierz spokojny, znany repertuar dopasowany do osoby i sytuacji. Krótka forma, kontakt wzrokowy i reakcja mieszkańca są ważniejsze niż długość występu.</p>
      <ul>
        <li>utwory wspomnieniowe i religijne</li>
        <li>spokojne melodie skrzypcowe</li>
        <li>piosenki znane z młodości</li>
        <li>krótkie życzenia muzyczne</li>
      </ul>
    </div>
  `, "blue", true);
}

function go(name){
  history.pushState({screen:name},"","#"+name);
  render(name);
}

function render(name){
  const route = name || location.hash.replace("#","") || "home";
  if(route==="home") home();
  else if(route==="tz") tz();
  else if(route==="goalsIntro") goalsIntro();
  else if(route==="mrm") mrm();
  else if(route==="theory") theory();
  else if(route==="ideas") ideas();
  else if(route==="zajecia") zajecia();
  else if(route==="pokoje") pokoje();
  else home();
}

window.go=go;
window.goalPage=goalPage;
window.stage=stage;
window.addEventListener("popstate",()=>render(location.hash.replace("#","")||"home"));
render();
