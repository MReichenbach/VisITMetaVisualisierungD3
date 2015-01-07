[VisITMetaVisualisierungD3][5]
=========
IF-MAP-Graphen Visualisierung mit D3, dem Dataservice aus dem Projekt [VisITMeta][3].
Inspiriert durch das [d3-process-map][4] - Beispiel.

Features
========
Ein IF-MAP-Graph kann statisch aus einer JSON-Datei erstellt werden.
Dabei muss diese dem Format der REST-Schnittstelle vom Dataservice, aus dem VisITMeta Projekt, entsprechen. 
Ebenfalls ist aber auch das Senden einer GET-Anfrage zur GraphResource des Dataservice möglich.

Dabei ist aber die VisITMeta-Configuration zu beachten (siehe unten).
Identifier werden als 'rect' dargestellt und Metadaten als 'ellipse'.
Sämtliche Properties eines Identifiers oder Metadatums werden angezeigt sobald der Cursor über solch einem Knoten positioniert wird.
Dabei wird auch der gesamte Graph ausgeblendet, bis auf dem Knoten über dem sich der Cursor befindet und dessen Kanten sowie deren Knoten.

Konfiguration
=============
Beschreibung der nötigen Einstellungen zur erfolgreichen Ausführung.

VisITMeta configuration(Dataservice)
-----------------------
Die aktuelle implementierung der "GraphResource" vom dataservice erlaubt es nicht "Cross-Origin-Requests" (COR) zu senden.
Dies ist nötig damit "VisITMetaVisualisierungD3" Requests absetzen kann, auch wenn sie nicht auf der selben Domäin läuft.
Unter extension/GraphResource.java ist eine modifizierte Version zu finden wo dies durch [CORS][2] dennoch möglich ist.

Ausführen
=======
1. Um eine einfache Visualisierung zu starten genügt es "visitmetaD3.html" im Browser zu öffnen und bei der Frage auf "Abbrechen"
zu klicken. Daraufhin wird ein statischer Graph aus der Datei "data/metadata_viel.json" erstellt.

2. Um den aktuellen Graphen aus einem laufenden Dataservice abzufragen, muss dieser erst wie unter dem Punkt „VisITMeta configuration(Dataservice)“ beschrieben verändert werden.

Lizenz
=======
VisITMetaVisualisierungD3 unterliegt der [Apache License, Version 2.0][1].

Sonstiges
=======
Getestet mit Firefox 33.1

----

[1]: http://www.apache.org/licenses/LICENSE-2.0.html
[2]: http://de.wikipedia.org/wiki/Cross-Origin_Resource_Sharing
[3]: https://github.com/trustathsh/visitmeta
[4]: https://github.com/nylen/d3-process-map
[5]: https://github.com/MReichenbach/VisITMetaVisualisierungD3