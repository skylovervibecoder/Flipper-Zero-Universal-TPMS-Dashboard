# Universal TPMS Dashboard

Evoluzione di "Nissan TPMS Dashboard". Il codec Nissan/Renault resta quello nativo
della tua app (invariato). In piu' supporta i protocolli di TPMS-Editor-EN
(altruista86, su core ProtoView di antirez).

## Compilare
Copia la cartella `universal_tpms_dashboard` in `applications_user/` (o usa uFBT) e:
    ufbt build        (oppure:  ufbt launch)
Il vecchio `nissan_dashboard` puo' restare installato: sono due app distinte.

## Protocolli
Verificati: Renault, Pacific C210/Toyota, Schrader, Schrader EG53MA4, VDO/PSA/FCA, Ford
TEST: Toyota PMV-107J (315 MHz), VDO TG1C, Shenzhen Q85, Mercedes Sprinter
EXP:  BMW Gen2/3, Elantra/Honda, Hyundai VDO, Truck Solar, Renault 0435R, Honda TRW, Porsche, Kia
(nell'app: "TST" = TEST, "EXP" = sperimentale)

## Uso
- Settings > Proto: Nissan/Renault (come prima) | AUTO detect | un protocollo specifico.
- Settings > Radio: profilo radio (315/433 x FSK/OOK/GFSK) o AUTO (ruota ogni 2,5 s).
- Pair sensors: con AUTO rileva protocollo e profilo da solo; i 4 sensori assegnati
  devono avere lo stesso protocollo. Salvando l'auto si salvano protocollo, radio e
  payload catturato di ogni ruota.
- Transmit: per i protocolli non nativi riscrive solo ID e pressione sul payload
  catturato in PAIR (il resto del frame resta identico, checksum ricalcolato).
  Senza PAIR usa i valori predefiniti del protocollo.
- Cambiare protocollo azzera gli ID: riaccoppia i sensori o digitali a mano.

## Dati
Cartella: /ext/apps_data/universal_tpms_dashboard/ . Al primo avvio copia auto e config
dalla vecchia apps_data/nissan_dashboard (gli originali non vengono toccati).

## Licenze
- protocols/proto6: core ProtoView (BSD-3, vedi PROTOVIEW_LICENSE).
- rx18_verified_more.c / rx19_exp.c: derivati da rtl_433 (GPL-2.0): se distribuisci l'app
  pubblicamente, il pacchetto va rilasciato con licenza compatibile e sorgenti.
- UI/encoder: TPMS-Editor-EN di altruista86 (nel repo non c'e' un file di licenza:
  per distribuire chiedi il permesso all'autore e lascia i crediti).
