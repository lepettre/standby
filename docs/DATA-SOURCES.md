# Datenquellen und Schnittstellen

Stand 3.0.0. Alle Abrufe laufen direkt im Browser, ohne eigenen Server. Lizenzen und Pflichtnennungen: CREDITS.md.

## Open-Meteo (Wetter)

- **Vorhersage:** `https://api.open-meteo.com/v1/forecast`
  - `current`: temperature_2m, apparent_temperature, relative_humidity_2m, weather_code, wind_speed_10m, wind_gusts_10m, wind_direction_10m, pressure_msl, is_day, uv_index
  - `hourly`: temperature_2m, precipitation_probability, precipitation, weather_code, snowfall
  - `daily`: weather_code, temperature_2m_max, temperature_2m_min, precipitation_probability_max, precipitation_sum, snowfall_sum, uv_index_max, sunrise, sunset
  - `forecast_hours=48`, `forecast_days=7`, `timezone=auto`
- **Luftqualität und Pollen:** `https://air-quality-api.open-meteo.com/v1/air-quality`, `current=european_aqi`, `hourly=alder_pollen,birch_pollen,grass_pollen,mugwort_pollen,ragweed_pollen`, `forecast_hours=24`. Pollen nur Europa und in der Saison.
- **Ortssuche:** `https://geocoding-api.open-meteo.com/v1/search`
- **Takt:** alle 15 Minuten. Zeiten kommen als Ortszeit ohne Zone; umgerechnet über `utc_offset_seconds`.
- **Wettercodes:** WMO-Codes, übersetzt in `wmo()`.

## Kalender

- **ICS-Abos:** Adresse(n) in den Einstellungen, Abruf meist über CORS-Proxy. Eigener Parser `parseICS()` mit Wiederholungen (`expand()`: RRULE mit FREQ, INTERVAL, COUNT, UNTIL, BYDAY, BYMONTHDAY), EXDATE, Ganztages-Terminen, LOCATION, DESCRIPTION. Termine mit TZID erscheinen in Gerätezeit.
- **Google Calendar API v3:** `https://www.googleapis.com/calendar/v3`, Anmeldung über Google Identity Services (`https://accounts.google.com/gsi/client`), Token-Modell, Bereich `https://www.googleapis.com/auth/calendar.readonly`. Token 1 Stunde gültig, danach Tipp zum Erneuern. Kalenderauswahl per Häkchen, je Widget wählbar (`S.wcal`).
- **Bekannter Fehler 3.0:** „The OAuth client was not found“, 401 invalid_client (siehe ROADMAP 3.0.1, Punkt 11).
- **Takt:** 15 Minuten.

## Spotify

- **Anmeldung:** Authorization Code mit PKCE, `https://accounts.spotify.com/authorize`, Token über `https://accounts.spotify.com/api/token`, Erneuerung per Refresh-Token. Eigene Client-ID nötig (Spotify Developer Dashboard), Redirect-URI = Dashboard-Adresse.
- **Bereiche:** user-read-playback-state, user-modify-playback-state, user-read-currently-playing, user-read-recently-played, playlist-read-private, playlist-read-collaborative, user-library-read, user-library-modify, streaming, user-read-email, user-read-private.
- **Endpunkte:** `/me/player`, `/me/player/devices`, `PUT /me/player` (Gerät wechseln), `/me/player/play|pause|next|previous|seek|volume|shuffle|repeat`, `/me/player/queue`, `/me/player/recently-played`, `/me/playlists`, `/me/tracks/contains`, `PUT|DELETE /me/tracks`.
- **Web Playback SDK:** `https://sdk.scdn.co/spotify-player.js`, macht den Desktop-Browser zum Lautsprecher; auf iPhone nicht unterstützt.
- **Takt:** 5 Sekunden, nur wenn ein Spotify-Widget sichtbar ist.
- **Bekannte Fehler 3.0:** Nicht-JSON-Antworten werden als JSON gelesen, Ratenbegrenzung 429 (siehe ROADMAP 3.0.1, Punkt 9). Steuerung nur mit Premium.

## Nachrichten

RSS 2.0 und Atom, Abruf meist über CORS-Proxy, Takt 15 Minuten. Voreinstellung ab 3.0.5: `https://www.tagesschau.de/index~rss2.xml`.

## Wikipedia

`https://de.wikipedia.org/api/rest_v1/feed/featured/JJJJ/MM/TT` (Artikel des Tages, Was geschah heute, Meistgelesen); Ersatz für leeres „Was geschah heute“: `https://api.wikimedia.org/feed/v1/wikipedia/de/onthisday/selected/MM/TT`. Takt: täglich.

## PEGELONLINE

`https://www.pegelonline.wsv.de/webservices/rest-api/v2/stations/{NAME}/W/measurements.json?start=P1D`, Werte in cm. Voreinstellung „KÖLN“ (Name an der Quelle zu prüfen). Takt: 10 Minuten.

## Radio

Direkte MP3-Streams im `<audio>`-Element, AirPlay über `webkitShowPlaybackTargetPicker()` wenn Safari Ziele meldet, Media Session für Sperrbildschirm.

| Sender | Adresse |
| --- | --- |
| Deutschlandfunk | `https://st01.sslstream.dlf.de/dlf/01/128/mp3/stream.mp3` |
| Deutschlandfunk Kultur | `https://st02.sslstream.dlf.de/dlf/02/128/mp3/stream.mp3` |
| Deutschlandfunk Nova | `https://st03.sslstream.dlf.de/dlf/03/128/mp3/stream.mp3` |

Adressen in der Entwicklungsumgebung nicht prüfbar gewesen; auf dem Gerät testen.

## Unsplash

`https://api.unsplash.com/search/photos` mit Access Key (optional, in den Einstellungen). Gewähltes Foto wird von der API-Adresse geladen (Hotlink), `download_location` wird ausgelöst, Fotograf und Link werden gespeichert.

## Lokale Speicherung

| Speicher | Schlüssel | Inhalt |
| --- | --- | --- |
| localStorage | `sb_settings` | Einstellungen `S` (Voreinstellungen in `DEFAULTS`) |
| localStorage | `sb_dashes` | Ansichten und Module |
| localStorage | `sb_dash_v` | Version der Voreinstellungs-Migration (derzeit 5) |
| localStorage | `sb_sp_tok`, `sb_sp_ver` | Spotify-Token, Codeprüfer |
| localStorage | `sb_g_tok`, `sb_g_ok` | Google-Token, Verbindungsstatus |
| localStorage | `sb_rph_u` | Unsplash-Rezeptfotos mit Fotografennennung |
| localStorage | `sb_radio_i` | Zuletzt gewählter Sender |
| IndexedDB `standby` (Version 2) | Store `photos` | Eigene Fotos |
| IndexedDB `standby` | Store `rphotos` | Eigene Rezeptfotos |

Alles ist an die Adresse (Origin) gebunden. Wechselt die Adresse, sind die Daten dort nicht vorhanden; Export/Import kommt mit 3.2.0.

## CORS-Proxy

Frei eintragbar (`S.proxy`); Platzhalter `https://dein-proxy.example/`. Empfehlung: eigener Cloudflare-Worker.

Ab 4.0 liefert die Open-Meteo Geocoding API auch die Zeitzone (`timezone`); sie dient der Städteauswahl für Weltzeit und Weltkarte.

## Abfahrten (ab 4.5)

Eigener Cloudflare-Worker (Code nicht im Repo, Adresse nur auf dem Gerät in `sb_settings.transitUrl`). Endpunkte: `GET /stops?q=Name` oder `?lat=…&lon=…` → `{stops:[{id,name,city,types,lat,lon,d?}]}`; `GET /departures?id=Master:…` → `{deps:[{line,dir,type,min,delay,platform,cancelled}],ts}`. Zugangsdaten als Worker-Secrets `GTI_USER`, `GTI_PASS`.
