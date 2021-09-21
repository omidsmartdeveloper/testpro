# BlockPro
---

![banner]()

![badge]()
![badge]()
[![license](https://img.shields.io/github/license/:user/:repo.svg)](LICENSE)
[![standard-readme compliant](https://img.shields.io/badge/readme%20style-standard-brightgreen.svg?style=flat-square)](https://github.com/RichardLitt/standard-readme)

Einleitung?
---
Im Rahmen des BlockPro-Projekts wird ein Blockchainbasierter Herkunftsnachweis für erneuerbare Energien entwickelt, bei dem Transaktionen zwischen Energieerzeugern und Verbrauchern manipulations- und revisionssicher gespeichert werden. BlockPro erhebt genaue Daten für Peer-to-Peer-Transaktionen, sodass die jährliche Spitzenlast ausgeglichen und Netznutzungsentgelte eingespart werden. Derzeit arbeitet BlockPro an dem Beispiel Consolino2IPFS und erhält viertelstündlich den Zählerstand über einen optischen Lesekopf. Anschließend werden die Zählerdaten mit dem zugehörigen Wert der CID mittels SHA-256 gehasht und in das Inter Planetary File System geladen.

Das zweite Beispiel, das P2P-Demoprotokoll, ist eine Studie zur Funktionsweise von libp2p. Libp2p ist ein modulares System aus Protokollen, Spezifikationen und Bibliotheken, das zur Entwicklung von Peer-to-Peer-Netzwerk-Anwendungen verwendet werden kann. Da die Anzahl der geplanten Nutzer von BlockPro die maximale Verarbeitungskapazität von Doichain überschreiten würde, wenn beispielsweise alle 2 Millionen Solaranlagenbetreiber alle 15 Minuten ihre Zählerstände in die Doichain speichern, sollte zunächst nur eine Untergruppe an teilnehmenden Nodes ausgewählt werden. Dieser Auswahlprozess wird durch das P2P-Demoprotokoll durchgeführt. 

Zuerst stellt der Node über libp2p Verbindungen zu anderen Nodes her. Anschließend veröffentlichen sie eine Zufallsnummer über publish and subscribe und vergleichen sie mit derselben zufällig generierten Lösungszahl. Derjenige Node, dessen Zahl am nächsten zur Lösung liegt, wird ausgewählt, die ebenfalls über publish und subscribe empfangenen Zählerstände der anderen Teilnehmer sowie die Eigenen in ein Dokument zusammenzufügen. Die Zählerstände werden dabei nicht direkt empfangen, sondern in Form einer CID, die der Pfad zum Zählerstand auf dem Inter Planetary File System ist. 

Diese Liste an CIDs wird wiederum ins IPFS hochgeladen und mittels SHA-256 verhasht. Der "Gewinner-Node" schreibt anschließend den SHA-256 Hash als name zusammen mit der CID in die Liste aller gesammelter CIDs im IPFS als value in die Doichain. So können die anderen Teilnehmer ihre eigene CID auf der Liste suchen und mit dem Hash verifizieren, dass ihr Zählerstand manipulationssicher in der Doichain gespeichert wurde.


## Table of Contents

- [Einleitung](#Einleitung)
- [Background](#background)
- [Get Started](#Get Started)
- [Usage](#usage)
- [API](#api)
- [Contributing](#contributing)
- [License](#license)

## Security

### Any optional sections

## Background

### Any optional sections

## Get Started with P2P-Demoprotokoll

1. git clone this repo 
2. run ```npm i``` in root directory
3. run ```docker-compose up``` to start 3 p2plib hosts in the docker environment
4. configure doichain node to publish new blockhashes to topic "rawblock": Start doichain daemon with: ```doichaind -zmqpubrawblock=tcp://127.0.0.1:28332```
or add ```zmqpubrawblock=tcp://127.0.0.1:28332``` to .doichain/doichain.conf
5. connect to peer1 ```docker-compose exec peer1 bash```and run from /js-libp2p/examples/pubsub ```npm run peer1```
6. connect to peer2 ```docker-compose exec peer1 bash``` and run from /js-libp2p/examples/pubsub ```npm run peer2```
7. connect to peer3 ```docker-compose exec peer3 bash``` and run from /js-libp2p/examples/pubsub ```npm run peer3```


```
```

### Any optional sections

## Usage

```
```

Note: The `license` badge image link at the top of this file should be updated with the correct `:user` and `:repo`.

### Any optional sections

## API

### Any optional sections

## More optional sections

## Contributing

See [the contributing file](CONTRIBUTING.md)!

PRs accepted.

Small note: If editing the Readme, please conform to the [standard-readme](https://github.com/RichardLitt/standard-readme) specification.

### Any optional sections

## License

[MIT © Richard McRichface.](../LICENSE)
