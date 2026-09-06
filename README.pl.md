# Echo + Argus — Chief of Staff z researcherem i pętlą informacji zwrotnej

[English](README.md) · [Nederlands](README.nl.md) · [Deutsch](README.de.md) · [Polski](README.pl.md) · [Español](README.es.md)

To nie pusty szablon — to dziennik, który pamięta, dlaczego coś postanowiłeś, żebyś nie musiał tłumaczyć tego dwa razy.

Echo zapisuje każdą decyzję razem z powodem, a później z rezultatem. Zatrzymuje się sam, gdy tylko coś się psuje, zamiast brnąć dalej po błędzie albo na starej kopii. I dostosowuje swoje zachowanie do tego, co odrzucasz — pod warunkiem, że dopiszesz dlaczego.

## Wklej to do nowego Grok Bota

    Jesteś Echo, moim chief of staff. Sklonuj to repo do /workspace/<nazwa-repo>, jeśli tego katalogu jeszcze nie ma, i zrób pull. Przeczytaj VM-GEHEUGEN.md oraz onboarding-interview.md. Przeprowadź wywiad onboardingowy — jedno pytanie naraz. Czekaj na moje odpowiedzi. Sprawdź moje zdalne repozytorium git i konektor. Żadnego pusha ani rutyn przed zakończeniem onboardingu.

Potrzebny jest tylko git: wybrane przez ciebie zdalne repozytorium plus konektor gita w Grok Bocie.

Startuje bez dostępu do twojej poczty i kalendarza. Poprosi o niego dopiero wtedy, gdy jakieś zadanie naprawdę tego wymaga.

## Co dostajesz

To, co dostajesz, jest podstawą, a nie gotowym systemem. Echo jeszcze cię nie zna. Licz się z miesiącem wdrażania: dawaj mu prawdziwe zadania, odrzucaj z podaniem powodu i sprawdzaj, czy następnym razem zrobi to inaczej. Po to właśnie jest dziennik. Jeśli poświęcisz ten miesiąc, będziesz mieć chief of staff dopasowanego do siebie. Jeśli tego nie zrobisz, zostanie szablonem.

## Słowniczek

- **Karta** — session card: jedna notatka na przebieg, z PASS/FAIL i tym, co następnym razem pójdzie inaczej. Brak karty = przebieg się nie liczy.
- **Lock** — reguła utrwalona, bo coś poszło źle dwa razy albo bo powiedziałeś "lock".
- **Zlecenie** — formularz, którym Echo deleguje: cel, nie-cel, input, done, termin, eskalacja.
- **Heartbeat** — dowód, że bot wciąż żyje: wpis w oczekiwanym dniu. Cisza dowodem nie jest.
- **Czerwone** — awaria protokołu. Jest zgłaszana i zatrzymywana, a nie po cichu obchodzona.
- **Skarbiec / biurko** — skarbiec to twoje zdalne repozytorium git, biurko to katalog roboczy na VM.
- **Rotacja** — stare wiersze logu są streszczane, gdy log robi się za długi.
- **Compaction** — to samo dla pamięci: streszczać, zamiast ciągnąć wszystko za sobą.

## Szybki start

1. Nowy Grok Bot: wklej `echo-profile.md` jako system prompt.
2. Dwa kolejne boty: `argus-profile.md` jako researcher, `athena-profile.md` jako audytor. Athena powinna być osobnym botem — bot audytujący sam siebie ma martwe pole.
3. Użyj `echo-routines.md` jako pliku z rutynami.
4. Opcjonalnie: podłącz Firecrawl albo Exa do Argusa. Działa też bez tego — Argus korzysta wtedy z tego, co Grok Bot potrafi sam.
5. **Wymagane:** wybrane zdalne repozytorium git oraz konektor gita w Grok Bocie.
6. Wklej prompt powyżej (dostosuj URL do klonowania, jeśli używasz forka).
7. Athena robi najpierw kontrolę konfiguracji, potem heartbeat w niedzielę. Brak audytu przez 8 dni = czerwone.

## Skarbiec to wybrane przez ciebie zdalne repozytorium git

- **GitHub albo GitLab** — za darmo, prywatne repo, dla większości w zupełności wystarczy.
- **Codeberg** — europejski, bez big techu.
- **Gitea albo Forgejo we własnym homelabie** — wszystko u siebie w domu.

Nie masz jeszcze konta? [github.com/signup](https://github.com/signup) to najszybsza opcja.

## Dlaczego to jest inne

- **Dziennik decyzji z powodem i rezultatem** — dlaczego, co zostało odrzucone i czy słusznie.
- **Pętla zwrotna** — każde odrzucenie dostaje krótkie uzasadnienie. Argus dostosowuje do tego dobór źródeł.
- **Kill switch** — trigger, stop, powiadomienie, unlock. Zobacz `echo-routines.md`.
- **Cichy bot** — brak outputu przez 7 dni, mimo że oczekiwano pracy = czerwone, żadnego "cisza znaczy, że działa".
- **Nieudany pull = stop** — jeśli pull się nie powiedzie, Echo nie pracuje dalej na starej kopii.
- **Bot researcherski** — Argus z oceną jakości źródeł. Zadania po onboardingu pochodzą z session memory, a nie z zaszytych rutyn side-hustle.
- **Trzy główne rutyny** — priorytety dzienne, podsumowanie tygodniowe (markdown, bez HTML), kontrola dziennika ryzyk. Plus audyt Atheny i audyt workflow.
- **Oszczędność tokenów** — zwięzłe logi, batching, żadnych pożeraczy HTML, rotacja po 50 wpisach.
- **Trigger repo** — "sprawdź repo i zrób aktualizację".
- **Pamięć trwała na VM** — jedno prawo: `VM-GEHEUGEN.md`.
- **Athena** — osobny bot audytora + heartbeat, plus twoja własna niedzielna kontrola, bo bot, który zamilkł, sam nie zgłosi swojego milczenia.

## Co jest w środku

- `echo-profile.md` — kim jest Echo (rola). Nie runbook.
- `echo-routines.md` — harmonogram: trigger, input, output, done, fail.
- `athena-profile.md` — audytor. Osobny bot; Echo gra tę rolę tylko awaryjnie.
- `argus-profile.md` — researcher. Zadania z session memory.
- `taakbrief-template.md` — obowiązkowy przy każdej delegacji.
- `decisions-log-template.md` — format logu + przykład dobry/zły.
- `VM-GEHEUGEN.md` — jedyne źródło prawdy dla pull/praca/karta/push i rotacji.
- `onboarding-interview.md` — dwie ścieżki, podsumowanie zwrotne, kontrola konfiguracji, pierwszy przebieg.
- `state/` — pamięć trwała.

Uwaga: pliki profili i state są napisane po niderlandzku, bo w tym języku pracuje Echo i jego zespół.

## Licencja

MIT — do swobodnego użytku i modyfikacji.
