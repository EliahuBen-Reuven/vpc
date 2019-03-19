---

copyright:
  years: 2017, 2018, 2019

lastupdated: "2019-02-20"


---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:download: .download}


# Prezzi per VPC
{: #pricing-for-vpc}

La tabella riepiloga i prezzi per il trasferimento dati su Internet con {{site.data.keyword.cloud}} Virtual Private Cloud. Ricorda che non vi è alcun costo per il traffico tra i servizi IBM Cloud VPC e classico. Inoltre, per i servizi PayGo, i livelli di servizio sono associati al tuo account, non a un'istanza VPC specifica. Gli importi sono indicati in dollari statunitensi.

Si applicano prezzi separati per le [istanze del server virtuale](/docs/infrastructure/vpc?topic=vpc-pricing-for-virtual-servers-for-vpc) utilizzate nel tuo IBM Cloud VPC.

## Franchigie per il trasferimento dati su Internet

| Trasferimento dati |  Costo per tutti i clienti di IBM Cloud VPC |
|---------------|------------------|
| All'interno della zona | Gratuito |
| Tra zone nella stessa regione | Gratuito |
| Utilizzo del gateway pubblico | Gratuito (addebitato solo per l'IP mobile utilizzato da PGW) |

## Prezzi per l'IP mobile

Un IP mobile viene addebitato alla tariffa di $1 (USA) al mese, a partire dalla data di prenotazione. La tariffa viene addebitata anche se l'IP mobile non è associato a una VSI o non è in uso. Il costo di $1 per la tariffa mensile viene addebitato anche se l'IP mobile è riservato solo per pochi giorni.


## Prezzi PayGo di base per il trasferimento dati su Internet

| Trasferimento dati | Quantità di dati | Prezzi PayGo |
|-----------|-----------|------------------|
| In uscita su Internet |  Da 0 a 5 GB | Gratuito |
|  | Da 6 a 10.000 GB | $0,087 per GB |
|  | Da 10.001 a 50.000 GB | $0,083 per GB |
|  | Da 50.001 a 150.000 GB | $0,07 per GB |
|  | 150.001 GB e oltre | $0,05 per GB |


Quando crei un nuovo VPC, potrebbe essere necessario attendere fino a un'ora per visualizzare i costi di fatturazione iniziali nell'API o nell'interfaccia utente della console.
{: tip}

Se disponi di un gateway pubblico o di un IP mobile, potresti comunque vedere alcuni addebiti in uscita minimi, anche se non hai inviato alcun traffico in uscita durante tale periodo. Questi addebiti sono per il traffico ARP, che è necessario per gestire il tuo account.
{: important}


