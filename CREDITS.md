# Quellen, Lizenzen und Würdigung

Stand: Version 3.1.3, 31. Oktober 2026. Diese Datei nennt alles, was in das StandBy-Dashboard eingeflossen ist oder von ihm genutzt wird: Daten, Schnittstellen, Schriften, Icons, Bilder, Texte, Werkzeuge und Vorbilder. Jeder neue Baustein bekommt hier einen Eintrag, bevor er ausgeliefert wird (siehe Regel in CLAUDE.md).

Legende Status: **geprüft** = Lizenz/Bedingung an der Quelle nachgelesen · **übernommen** = aus Sekundärquelle, an der Primärquelle noch zu bestätigen · **offen** = Urheber oder Bedingung unbekannt, vor Weitergabe klären.

Umsetzung im Dialog mit Claude (Anthropic).

## 1. Daten und Schnittstellen

| Quelle | Wofür | Lizenz / Bedingung | Pflicht im Dashboard | Stand in 3.0 | Status |
| --- | --- | --- | --- | --- | --- |
| Open-Meteo Forecast API (open-meteo.com, Open-Meteo, Schweiz) | Wetter jetzt, stündlich, 7 Tage, UV, Schnee, Sonnenzeiten | Daten CC BY 4.0; kostenlose API nur nicht-kommerziell, unter 10 000 Aufrufe/Tag, 5 000/Std., 600/Min.; Quellcode AGPLv3 | Hinweis „Weather data by Open-Meteo.com“ mit Link nahe jeder Wetteranzeige; Änderungen kenntlich machen | Kein sichtbarer Hinweis | geprüft (open-meteo.com/en/terms, /en/pricing) |
| Wettermodelle hinter Open-Meteo (u. a. DWD, NOAA, ECMWF, Météo-France, CMC) | Rohdaten der Vorhersagen | Je nach Dienst; Open-Meteo nennt sie als Grundlage | Nach Open-Meteo-Lizenzseite nennen | Kein Hinweis | übernommen |
| Open-Meteo Air Quality API | Luftqualität (European AQI), Pollen (Erle, Birke, Gräser, Beifuß, Ambrosia) | Wie Open-Meteo; Daten stammen vom Copernicus Atmosphere Monitoring Service (CAMS), der eine eigene Quellenangabe verlangt | Open-Meteo und CAMS nennen | Kein Hinweis | übernommen (CAMS-Wortlaut an der Quelle prüfen) |
| Open-Meteo Geocoding API | Ortsname zu Koordinaten | Wie Open-Meteo; Ortsdaten basieren auf GeoNames (CC BY 4.0) | Open-Meteo, GeoNames nennen | Kein Hinweis | übernommen |
| PEGELONLINE REST-API v2 (Wasserstraßen- und Schifffahrtsverwaltung des Bundes, WSV) | Wasserstand, Standard-Messstelle Köln (Name an der Quelle zu prüfen) | Laut Sekundärquellen Datenlizenz Deutschland – Zero – 2.0; Rohdaten ohne Prüfung und Gewähr | Freiwillig: „Datenquelle: PEGELONLINE der WSV“; nicht für sicherheitskritische Entscheidungen | Quelle im Detailfenster genannt | übernommen (auf pegelonline.wsv.de bestätigen) |
| Wikipedia REST-Feed (de.wikipedia.org/api/rest_v1/feed/featured) und Wikimedia Feed API (api.wikimedia.org/feed/v1) | Was geschah heute, Artikel des Tages | Texte CC BY-SA 4.0; Wikimedia-Nutzungsbedingungen und API-Richtlinien (User-Agent, faire Nutzung) | Wikipedia als Quelle, Lizenz, Link zum Artikel | „Quelle: Wikipedia, CC BY-SA“ im Detailfenster; Links fehlen im Widget | übernommen |
| Spotify Web API und Web Playback SDK (Spotify AB) | Wiedergabe, Geräte, Warteschlange, Playlists, Bibliothek; Browser als Lautsprecher | Spotify Developer Terms, Developer Policy, Design & Branding Guidelines | Spotify-Logo bei jeder Spotify-Anzeige; Cover unverändert, nicht beschnitten, keine Überlagerung, keine Steuerung auf dem Cover; Metadaten verlinken zurück zu Spotify | **Verstößt**: Cover vollflächig beschnitten, getönt, Text und Knöpfe darüber, kein Logo | geprüft (developer.spotify.com/documentation/design) |
| Google Calendar API v3 und Google Identity Services | Termine lesen | Google APIs Terms of Service, Google API Services User Data Policy | Nur Lesezugriff, Datenschutzhinweis bei Veröffentlichung | Nur Lesen umgesetzt | übernommen |
| Unsplash API | Rezeptfotos, von dir ausgewählt | Unsplash License für Fotos; API Guidelines: Bilder nur über die von der API gelieferten Adressen laden, Fotograf und Unsplash nennen und verlinken (mit utm-Parametern), Download-Endpunkt bei Verwendung auslösen, Schlüssel vertraulich halten | Nennung „Foto: Name / Unsplash“ mit Links | Hotlink, Download-Auslösung und Nennung umgesetzt; utm_source „standby“ ist kein registrierter App-Name | geprüft (help.unsplash.com API Guidelines) |
| Zwei Unsplash-Fotos als Demo-Bilder (photo-1506744038136-46273834b3fb, photo-1511884642898-4c92249e20b6) | Fotos-Widget im Demo-Modus | Unsplash License | Fotograf nennen | **Keine Nennung, Fotograf nicht ermittelt** | offen: ersetzen oder Urheber nachtragen |
| RSS-Feed tagesschau.de (tagesschau.de/index~rss2.xml, ARD-aktuell / NDR) | Voreingestellte Schlagzeilen, ab 3.0.5 | Nutzungsbedingungen von tagesschau.de; Schlagzeilen sind redaktionelle Inhalte | Quelle nennen, verlinken | Feedname im Widget, Schlagzeilen verlinkt | offen |
| Vorgeschlagene Nachrichten-Feeds (tagesschau, ZEIT ONLINE, Süddeutsche Zeitung, FAZ, heise online, netzpolitik.org, BBC News, The Guardian, NPR, Al Jazeera, The New York Times) | Vorschläge im Feed-Feld, ab 4.3.0 | Nutzungsbedingungen der jeweiligen Anbieter; Schlagzeilen sind redaktionelle Inhalte | Quelle (Domain) im Widget, Schlagzeilen verlinkt | Domain im Widget, Link zum Artikel | offen (Adressen nicht abrufbar geprüft) |
| Livestreams Deutschlandradio (Deutschlandfunk, Deutschlandfunk Kultur, Deutschlandfunk Nova) | Radio | Öffentlich angebotene Streams für privates Hören; keine Logos verwendet | Sendername nennen | Name genannt | übernommen |

## 2. Inhalte

| Quelle | Wofür | Lizenz / Bedingung | Status |
| --- | --- | --- | --- |
| „Die Gestirne“, früheres eigenes Projekt | Zitate, Mondzeichen, Pixel-Planeten, Pixel-Porträts, Papierfarbe, Gestaltung | Eigenes Werk | geprüft |
| 32 Zitate von Theodor W. Adorno, Max Horkheimer, Walter Benjamin, Herbert Marcuse | Inhalt der Gestirne | Kurze Zitate mit Quellenangabe (Zitatrecht, § 51 UrhG). Adorno († 1969), Horkheimer († 1973), Marcuse († 1979): Werke noch geschützt; Benjamin († 1940): gemeinfrei | übernommen (Zitatzweck bei Weitergabe prüfen) |
| 35 Rezepte aus einer eigenen Rezepte-App, Export vom 31.10.2026 | Kochmodus, Rezept-Kachel | Quellen je Rezept in Abschnitt 6; Rezepttexte teils aus Verlagsquellen, nur für private Nutzung | übernommen |
| Metrische Ergänzungen in drei englischen Rezepten (Vegan Mapo Tofu, Aubergine and puy lentils, Citrus Mackerel Spaghetti) | Umrechnung, mit ≈ markiert | Eigene Berechnung | geprüft |

## 3. Schriften

| Schrift | Urheber | Lizenz | Einbindung | Status |
| --- | --- | --- | --- | --- |
| Archivo Black | Omnibus-Type | SIL Open Font License 1.1 | Base64 eingebettet (aus einer eigenen Rezepte-App übernommen); Lizenztext `lizenzen/OFL-ArchivoBlack.txt` (aus Fontsource 5.3.0), Nennung unter „Über und Quellen“ | übernommen |
| Space Mono | Colophon Foundry, für Google Fonts | SIL Open Font License 1.1 | Base64 eingebettet (aus einer eigenen Rezepte-App); Lizenztext `lizenzen/OFL-SpaceMono.txt` (aus Fontsource 5.3.0), Nennung unter „Über und Quellen“ | übernommen |
| VT323 | Peter Hull (The VT323 Project Authors), Dateien über Fontsource `@fontsource/vt323` 5.3.0 | SIL Open Font License 1.1 | Copyright-Hinweis und Lizenz bei Weitergabe beilegen | Ab 3.0.1 als WOFF2 (latin, latin-ext) eingebettet; Hinweis im CSS-Kommentar, Lizenztext in `lizenzen/OFL-VT323.txt`; sichtbare Nennung unter „Über und Quellen“ (ab 3.1.3) | geprüft am Lizenztext des Pakets |
| SF Pro / SF Pro Rounded / New York | Apple | Systemschriften, nur über `ui-rounded`, `-apple-system`, `ui-serif` aufgerufen, nicht eingebettet | Systemaufruf | geprüft |

## 4. Icons und Grafik

| Element | Herkunft | Lizenz | Status |
| --- | --- | --- | --- |
| Spotify-Symbol (ab 3.1.0) | Pfad aus Simple Icons (simple-icons, npm), Marke von Spotify AB | Simple Icons: CC0 1.0 (Paketangabe gelesen); Markennutzung nach Spotify Design Guidelines | offen (Guidelines zu Logogröße, Farbe, Cover-Radius an der Quelle nachlesen) |
| App-Icon und Favicon (`icons/`, ab 3.0.2) | Eigenes Werk, gestaltet mit Claude nach dem eigenen Widget „Uhr als Ringe“ | eigenes Werk | – |
| Inline-SVG-Icons (39 Stück, u. a. cloud, moon, music, heart, repeat, radio, airplay, shuffle) | Pfade entsprechen weitgehend Lucide (lucide.dev), teils von Feather Icons abgeleitet; einige schlicht selbst gezeichnet (play, pause, grid) | Lucide: ISC License; Feather: MIT License | übernommen (Herkunft je Icon in Code prüfen, Lizenztext beilegen) |
| Landmaske der Punkt-Weltkarte (90 × 40 Raster) | Erzeugt mit dem Python-Paket global-land-mask (Todd Karin), das auf dem GLOBE-Höhenmodell der NOAA beruht | global-land-mask: MIT License; GLOBE-Daten: US-Regierung, frei | übernommen (Lizenz des Pakets prüfen) |
| Sonnenstand und Tag-Nacht-Grenze | Eigene Umsetzung gängiger astronomischer Näherungsformeln | – | geprüft |
| Bahnhofsuhr | Eigene schlichte Variante, bewusst nicht die geschützte SBB-Uhr (Gestaltung Hans Hilfiker) | – | geprüft |
| UV-Farbskala | Angelehnt an die Farbstufen des UV-Index der WHO | – | übernommen |

## 5. Vorbilder und Werkzeuge

| Was | Rolle | Lizenz / Hinweis |
| --- | --- | --- |
| Apple StandBy (iOS) | Gestalterisches Vorbild: Querformat, Schwarz, große Ziffern, Wackelmodus | Marken von Apple; kein Code oder Bild übernommen |
| KI-generiertes React-Mockup, als Vorlage eingereicht | Ausgangsidee, analysiert, nicht übernommen | Herkunft laut Vorlage KI-generiert |
| Zweite KI-Version, als Vorlage eingereicht | Analysiert, einzelne Ideen geprüft | wie oben |
| Python 3, Node.js, Playwright (Microsoft), Pillow, acorn | Bauen, Syntaxprüfung, Screenshots, Code-Index | PSF-Lizenz, MIT, Apache 2.0, MIT-CMU (HPND), MIT; nicht Teil der ausgelieferten Datei |
| Claude (Anthropic) | Umsetzung im Dialog | – |

## 6. Rezeptquellen (aus dem eingebetteten Rezept-Export)

| Rezept | Autorin/Autor | Quelle | Link |
| --- | --- | --- | --- |
| Rotes Linsen-Dal mit Kokos | – | Beispielrezept | – |
| Zitronen-Joghurt-Kuchen mit Glasur | – | Beispielrezept | – |
| Gebackener Blumenkohl mit Harissa-Pilaw | – | Zeit Magazin Wochenmarkt | – |
| Pasuts Tolma | – | – | – |
| Grüner Nudelsalat | Elisabeth Raether | Zeit Magazin 22/2026 | – |
| Fenchel-Bällchen | – | Zeit Magazin Wochenmarkt, Herbst 2026 | – |
| Borschtsch | – | – | – |
| Scherennudeln mit cremiger Kimchi-Soße | Eat this | – | – |
| Dinkelbrötchen mit Bärlauch | ichmachpizza | – | – |
| Johannisbeer-Tarte | – | – | – |
| Warmer Rotkohl-Salat | – | – | – |
| Sumach-Aubergine | – | – | – |
| Rote-Bete-Risotto | – | FAS, 26.09.2026 | – |
| Pilzgulasch | Tim Mälzer | ARD-Buffet | – |
| Saatenbrot | – | Studio Schmaus | – |
| Warmer Möhren-Linsen-Salat | fit_sophia_laetitia | – | https://www.instagram.com/reels/Dauna4Tt0Xj/ |
| Aubergine and puy lentils | – | Show up, the kitchen project at Bergen Prison | – |
| Schwarzwälder Kirschtorte | – | Schwäbisches Kochbuch | – |
| Ragù alla Bolognese | Marcella Hazan | – | – |
| Gurken-Feigen-Salat | Giusi_Food/Instagram | – | – |
| Kürbiscremesuppe | LeoDoppler.cooks/Instagram | – | – |
| Low-Carb-Bohnen-Carbonara | Noah Bachofen/Instagram | – | – |
| Zitronen-Mohn-Kuchen | Ottolenghi | – | https://www.zeit.de/zeit-magazin/2017/45/zitronenkuchen-mohn-rezept-wochenmarkt |
| Apfel-Zwiebel-Chutney | Manufactum | – | https://www.manufactum.de/apfel-zwiebel-chutney-c200056/ |
| Bärlauch-Maultaschen | Manufactum | – | https://www.manufactum.de/baerlauch-maultaschen-salat-c202522/ |
| Erdbeer-Rhabarber-Schnecken | Manufactum | – | https://www.manufactum.de/hefeschnecken-c202402/ |
| Steckrüben-Kimchi | – | – | https://www.milk-food.de/insights/magazin/sauerkraut-mal-anders/ |
| Rotkohl-Kimchi | – | – | https://www.milk-food.de/insights/magazin/sauerkraut-mal-anders/ |
| Weißkohl-Kimchi | – | – | https://www.milk-food.de/insights/magazin/sauerkraut-mal-anders/ |
| Kichererbsen-Eintopf aus dem Ofen | – | – | – |
| Citrus Mackerel Spaghetti with Pangrattato | Rosie Kellet | – | https://thehappyfoodie.co.uk/recipes/rosie-kellets-citrus-mackerel-spaghetti-with-pangrattato/ |
| Rösti mit Pilz-Maronen-Ragout | – | – | https://www.ikea.com/de/de/rooms/kitchen/how-to/rezept-plantbullar-mit-pilz-maronen-ragout-pub0c2831a0/ |
| Biang-Biang-Noodles | Sissi Cheng | – | https://www.zeit.de/zeit-magazin/wochenmarkt/2024-12/biang-biang-nudeln-china-rezept-wochenmarkt |
| Šaltibarščiai | Verena Lugert | – | https://www.spiegel.de/stil/rezept-fuer-kalte-rote-bete-suppe-aus-litauen-saltibarsciai-a-0ad0357e-4820-468c-ade5-3641900f6d19?sara_ref=re-so-app-sh |
| Vegan Mapo Tofu | Lisa Lin | – | https://healthynibblesandbits.com/vegetarian-mapo-tofu/ |

„–“ heißt: Im Export ist keine Quelle eingetragen. Diese Einträge vor jeder Weitergabe ergänzen; nichts davon wird hier erfunden.

## 7. Offene Pflichten (in der Roadmap als 3.1.0 eingeplant)

1. Open-Meteo-Hinweis mit Link an jeder Wetteranzeige, CAMS bei Luftqualität und Pollen. Stand 3.1.3: im Wetter-Detailfenster und unter „Über und Quellen“; in den Kacheln selbst noch nicht.
2. Spotify-Darstellung an die Design-Richtlinien anpassen: erledigt in 3.1.0, Richtlinien noch an der Quelle prüfen.
3. Demo-Fotos ersetzen oder Fotografen nachtragen: erledigt in 4.3.0 (eigene Symbolbilder).
4. Lizenztexte für OFL-Schriften, Lucide und global-land-mask: erledigt in 3.1.3 (`lizenzen/`, verlinkt unter „Über und Quellen“); für global-land-mask liegt kein Lizenztext im Paket, nur die Angabe MIT.
5. Wikipedia-Einträge im Widget und Detailfenster verlinken.
6. Unsplash utm_source auf den registrierten App-Namen setzen.
7. Alle „übernommen“-Einträge an der Primärquelle bestätigen.
