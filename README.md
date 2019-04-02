<h1>Podatkovno rudarjenje - PR19ZB</h1>
<h2>Podatkovno rudarjenje (Analiza aplikaciji objavljenih na Google Play store)</h2>

<h3>Univerza v Ljubljani</h3>
<h4>Fakulteta za računalništvo in informatiko</h4>

<h5>Skupina</h5>
<ul>
  <li>Žiga Benko 63170052</li>
</ul>

<h3>Podatki</h3>
<p>Kratek opis podatkov je bil predstavljen že v osnutku, tukaj pa bom na hitro še posebej opisal vse atribute in rešitve, ki jih nameravam predstaviti. Gre se za podatke o aplikacijah naloženih na Google Play store, link do podatkov je <a href="https://www.kaggle.com/lava18/google-play-store-apps">tukaj</a>.</p>
<p>Ker se mi zdi, da je na tem viru, kljub količini podatkov premalo atributov iz katerih bi lahko napovedal in razbral določene stvari, sem se odločil, da uporabim še drug vir podatkov o aplikacijah naloženih na Google Play, link do teh podatkov pa se nahaja <a href="https://old.datahub.io/dataset/google-play-statistics">tukaj</a>.</p>
<br>
<p>Vse podatke, ki sem jih pridobil iz spletne strani Kaggle hranim v direktoriju kaggle in enako velja za podatke iz opendata.</p>
<p>V direktoriju kaggle imam dve datoteki in sicer:</p>
<ul>
  <li>googleplaystore_user_reviews.csv,</li>
  <li>googleplaystore.csv</li>
</ul>

<p>Vsak podatek v zbirki ima sledeče atribute:</p>
<ul>
  <li><i>App: </i>ime aplikacije.</li>
  <li><i>Category: </i>kategorija kamor aplikacija spada.</li>
  <li><i>Rating: </i>skupna ocena uporabnikov.</li>
  <li><i>Reviews: </i>število mnenj, ki so jih podali uporabniki o tej aplikaciji.</li>
  <li><i>Size: </i>Velikost aplikacije.</li>
  <li><i>Installs: </i>Število prenosov/inštalacij aplikacije.</li>
  <li><i>Type: </i>Ali je aplikacija plačljiva ali brezplačna.</li>
  <li><i>Prize: </i>Cena aplikacije, če je le ta plačljiva.</li>
  <li><i>Content Rating: </i>Starostna skupina na katero aplikacije cilja.</li>
  <li><i>Genres: </i>Žanr kamor spada aplikacija (spada lahko v več žanrov hkrati).</li>
  <li><i>Content Last Updated:</i> Datum, ko je bila aplikacija nazadnje posodobljena na Google Play store.</li>
  <li><i>Cur Ver:</i> Trenutna verzija objavljene aplikacije.</li>
  <li><i>Android Ver:</i> Najmanjša zahtevana verzija sistema Android na katerem aplikacija lahko deluje.</li>
</ul>
<p>Poleg osnovne datoteke, ki vsebuje podane atribute, je še ena datoteka v kateri so shranjeni "reviewi" ~ mnenja uporabnikov in ali je bilo podano mnenje pozitivno ali negativno.</p>

<h3>Kaj me zanima?</h3>
<ul>
  <li>Lastnosti popularnih aplikacij,</li>
  <li>ocene določene aplikacije po državah,</li>
  <li>katera verzija sistema android se največkrat sesuje,</li>
  <li>odvisnosti atributov.</li>
</ul>
<h3>Pridobivanje podatkov</h3>
<p>Ker so vsi podatki hranjeni v formatu CSV, je njihovo branje še toliko enostavnejše in pregledno prebrati z Pythonovo knjižnico Pandas.</p>
<code>data = pd.read_csv("kaggle/googleplaystore.csv")</code>
<img src="images/tabela1.png"/>
<br>
<p>Seveda je bilo potrebno tudi preveriti, če so kakšni vnosi brez vrednosti (nastavljeni na null) in le te tudi odstraniti, saj bi lahko zavajali pri analizi rezultatov.</p>
