# Zadanie 1
Do projektu dodać .gitignore (chodzi o pliki związane z intellij) - sprawdź czy znikneły też z twojego repozytorium na gitlabie? 
**Odp.: Nie**
Co trzeba zrobić, żeby tak się stało? **Odp.: `git rm –cached -r ./.idea`**

# Zadanie 2
Zmienić brancha z powrotem na test. Jakie pojawiły się problemy jak można je rozwiązać? Opisz dwa sposoby.
**Odp.: Dostajemy error: Your local changes to the following files would be overwritten by checkout: pom.xml
Please commit your changes or stash them before you switch branches.
Czyli trzeba zrobić commit zmian lub wykonać stash (dzięki czemu zmiany zostaną przechowane jak w schowku) i dopiero wtedy checkout na branch test**

# Zadanie 3
Opisać jaka jest różnica między git checkout HEAD~3 i git reset --hard HEAD~3
**git checkout HEAD~3   – przeniesie HEAD o 3 commity wstecz oraz odczepi go od brancha (o ile był do jakiegoś przyczepiony)**

**Git reset --hard  HEAD~3 – wyczyści staging area i  wyczyści lokalne zmiany oraz przeniesie HEADa o 3 commity wstecz, razem z branchem do którego jest przyczepiony (o ile jest do jakiegoś przyczepiony)**

# Zadanie 4
Różnica między revert i reset: 
**Git reset możemy wykonać na 3 sposoby:
Git reset --hard wycofa zmiany, ale jest dość niebezpieczna opcja. Gdy jej użyjemy, to cofamy się do wybranego commita i kasujemy wszelkie zmiany, jakie były dokonane po tym commicie.
Gdy użyjemy opcji git reset --mixed lub nie podamy argumentu, to pliki zostaną zachowane, ale nie zostaną one zgłoszone do zatwierdzenia.
W przypadku git reset --soft cofniemy się do wybranego commita, jednakże wszelkie zmiany dokonane po commit nie zostaną usunięte. Plik ze zmianami będą widoczne jako "zmiany do potwierdzenia".
Git revert także, może cofnąć zmiany. Wykona ono za nas commita, który cofnie wprowadzone przez nas zmiany. I dzięki temu będziemy mieli w historii commit, który coś zmienił oraz commit, który tę zmianę cofnął. Git revert jest bezpieczniejszy od git reset, ponieważ w każdej chwili możemy cofnąć swoją „zmianę cofania”**

# Zadanie 5
Sprzątanie śmieci
Uruchomić komendę git clean -n przeanalizować co stało by się gdby nie było -n: 
**Odp.: git clean -n wyświetla nam listę plików do usuniecia(nie śledzonych), ale ich nie usuwa, natomiast git clean usunie pliki od razu**

**it remote prune -n origin - -n wylistuje nam zbęde branche do usunięcia lokalnie (których nie ma na zadalnym repozytorium), a bez „-n” branche zostaną od razu usuniętę

# Zadanie 6
Cherry-pick
Co robi opcja –nocommit – **Odp.: wrzuca zmiany na staging area i nie commituje ich od razu, dzięki temu można je przejrzeć i ewentualnie zmodyfikować**
