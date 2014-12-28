VisITMetaVisualisierungD3
=========
IF-MAP-Graphen Visualisierung, mit D3, des dataservice aus dem Projekt [VisITMeta][3].

Features
========
Ein IF-Map Graph kann statisch aus einer JSON-Datei erstellt werden. Dabei muss diese dem Format
der REST-Schnitstelle vom dataservice, aus dem VisITMeta Projekt, entsprechen.
Es ist aber auch möglich ein GET-Anfrage zur GraphResource des dataservice zu senden. Dabei ist aber die VisITMeta configuration zu beachten, siehe unten.

Identifier werden als 'rect' dargestellt und Metadaten als 'ellipse'.
Sämtliche properties eines Identifiers oder Metadatums werden angezeigt sobald der Cursor über solch einem Knoten positioniert wird.
Dabei wird auch der gesamte Graph ausgeblendet, bist auf dem Knoten über dem sich der Cursor befinde und dessen Kannten, sowie deren Knoten.

Configuration
=============
Beschreibung der nötigen Einstellungen, damit alles läuft.

VisITMeta configuration(dataservice)
-----------------------
Die aktuelle implementierung der "GraphResource" vom dataservice erlaubt es nicht "Cross-Origin-Requests" (COR) zu senden.
Dies ist nötig damit "VisITMetaVisualisierungD3" Requests absetzen kann, auch wenn sie nicht auf der selben Domäin läuft.
Unter extension/GraphResource.java ist eine modifizierte Version zu finden wo dies durch [CORS][2] dennoch möglich ist.

Running
=======
1. Um einfach was zu sehen genügt es "visitmetaD3.html" zu starten und bei der Frage auf "Abbrechen" zu klicken.
Daraufhin wird ein statischer Graph aus der Datei "data/metadata_viel.json" erstellt.

2. Um den current Graph aus einem laufenden dataservice abzufragen, muss dieser erst wie unter Configuration beschrieben verändert werden.

License
=======
VisITMetaVisualisierungD3 is licensed under the [Apache License, Version 2.0][1].

Sonstiges
=======
Getestet mit Firefox 33.1

----

[1]: http://www.apache.org/licenses/LICENSE-2.0.html
[2]: http://de.wikipedia.org/wiki/Cross-Origin_Resource_Sharing
[3]: https://github.com/trustathsh/visitmeta
