# Overpass-turbo skrypty
Skrypty  przydatne  w walidacji danych.

Skrypt wyszukuje drogi oznakowane jako "track" które mają nadaną nazwę i powinny mieć zmienioną kategorię
```
[out:json][timeout:250];
// zamień “Łódzkie” na nazwę województwa w którym chcesz szukać dróg
{{geocodeArea:łódzkie}}->.searchArea;
// gather results
(
  // zapytanie dla: “highway=track” i "name"=*
  way[highway=track][name](area.searchArea);
);
// print results
out body;
>;
out skel qt;
```
Link: https://overpass-turbo.eu/s/12em
