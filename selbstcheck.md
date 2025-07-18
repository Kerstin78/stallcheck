---
layout: default
title: Selbstcheck
---

# Basis-Selbstcheck (kostenlos)

<form id="checkForm">
  <ol>
    <li>Ist die Tränke jederzeit zugänglich? <br><input type="radio" name="q1" value="1"> Ja <input type="radio" name="q1" value="0"> Nein</li>
    <li>Gibt es täglich Auslauf oder Weidegang? <br><input type="radio" name="q2" value="1"> Ja <input type="radio" name="q2" value="0"> Nein</li>
    <li>Ist die Einstreu sauber und trocken? <br><input type="radio" name="q3" value="1"> Ja <input type="radio" name="q3" value="0"> Nein</li>
    <li>Werden die Tiere täglich kontrolliert? <br><input type="radio" name="q4" value="1"> Ja <input type="radio" name="q4" value="0"> Nein</li>
    <li>Ist die Fütterung angepasst und ausgewogen? <br><input type="radio" name="q5" value="1"> Ja <input type="radio" name="q5" value="0"> Nein</li>
    <li>Ist die Umgebung frei von Gefahrenquellen? <br><input type="radio" name="q6" value="1"> Ja <input type="radio" name="q6" value="0"> Nein</li>
  </ol>
  <button type="button" onclick="auswerten()">Auswertung anzeigen</button>
</form>
<div id="ergebnis"></div>

<script>
function auswerten() {
  let punkte = 0;
  for (let i = 1; i <= 6; i++) {
    const antwort = document.querySelector(`input[name=q${i}]:checked`);
    if (antwort) punkte += parseInt(antwort.value);
  }
  document.getElementById("ergebnis").innerHTML =
    `<p>Sie haben ${punkte} von 6 Punkten erreicht.</p>` +
    (punkte >= 5 ? "<p>Sehr gut! Ihr Stall erfüllt bereits viele wichtige Kriterien.</p>" : "<p>Es gibt noch Verbesserungspotenzial. Nutzen Sie unsere erweiterten Angebote für eine genauere Analyse.</p>");
}
</script>
