---

copyright:
  years: 2019
lastupdated: "2019-02-20"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:important: .important}
{:download: .download}
{:DomainName: data-hd-keyref="DomainName"}

# Creación de una VPC en una región distinta
{: #creating-a-vpc-in-a-different-region}

Una región es una ubicación geográfica específica en la que puede desplegar apps, servicios y otros recursos de {{site.data.keyword.cloud}}. Las regiones constan de una o más zonas, que son centros de datos físicos que alojan los recursos de cálculo, de red, de almacenamiento y los recursos relacionados con refrigeración y alimentación que alojan los servicios y las aplicaciones. Las zonas están aisladas unas de otras, lo que garantiza que no haya un punto único de error compartido.

Virtual Private Cloud se está desplegando en todas las regiones de IBM Cloud por fases.

|   Ubicación     | Región | Punto final de API | Estado |
| ------- | :------: | :------: |:------: |
| Dallas | us-south | `us-south.iaas.cloud.ibm.com`| Disponible |
| Frankfurt | eu-de | `eu-de.iaas.cloud.ibm.com`| Disponible |
| Washington DC | us-east | `us-east.iaas.cloud.ibm.com`| Próximamente |
| Tokio | jp-tok | `jp-tok.iaas.cloud.ibm.com`| Próximamente |
| Londres | eu-gb | `eu-gb.iaas.cloud.ibm.com`| Próximamente |
| Sídney | au-syd | `au-syd.iaas.cloud.ibm.com`| Próximamente |

El punto final de la API regional (VPC) se establece automáticamente mediante la CLI de IBM Cloud cuando se inicia una sesión en una región específica.
{: note}

## Inicie una sesión en una región específica utilizando la CLI

Cuando inicie la sesión en IBM Cloud, puede especificar una región o puede seleccionarla más adelante. Por ejemplo, para iniciar una sesión en el punto final de API global en la región de Dallas (`us-sur`) directamente, ejecute los mandatos siguientes, en función de si tiene una cuenta federada (SSO) o no.

Para una cuenta federada,

```
ibmcloud login -a https://cloud.ibm.com -r us-south --sso
```
{: pre}

Para una cuenta no federada,

```
ibmcloud login -a https://cloud.ibm.com -r us-south
```
{: pre}

Para elegir la región más adelante, no especifique el parámetro `-r <region>` y la CLI le solicitará que elija una región.

Resultado de ejemplo:

```
Punto final de API: cloud.ibm.com

Obtener código de un solo uso de https://identity-2.eu-central.iam.cloud.ibm.com/identity/passcode para continuar.
¿Abrir el URL en el navegador predeterminado? [S/n]> s
Código de un solo uso >
Autenticando...
Correcto

Seleccione una cuenta:
1. MyAccount (00a11aa1a11aa11a1111a1111aaa11aa) <-> 1234567
2. TeamAccount (2bb222bb2b22222bbb2b2222bb2bb222) <-> 7654321
Introduzca un número> 2
Cuenta de destino TeamAccount (2bb222bb2b22222bbb2b2222bb2bb222) <-> 7654321


Grupo de recursos de destino Predeterminado

Seleccione una región (o pulse Intro para omitir):
1. au-syd
2. jp-tok
3. eu-de
4. eu-gb
5. us-south
6. us-east
Introduzca un número> 5
Región de destino us-south


Punto final de API: https://cloud.ibm.com
Región:             us-south
Usuario:            first.last@email.com
Cuenta:             TeamAccount (2bb222bb2b22222bbb2b2222bb2bb222) <-> 7654321
Grupo de recursos:  Predeterminado
Punto final de API de CF:
Organización:
Espacio:

...
```
{: screen}

## Cambio de regiones mediante la CLI

Para obtener el estado más reciente de las regiones VPC disponibles, ejecute el mandato siguiente:

```
ibmcloud is regions
```
{: pre}

Para cambiar a otra región, ejecute el mandato `ibmcloud target -r <region>`. Por ejemplo, para cambiar a la región Frankfurt, ejecute el siguiente mandato:

```
ibmcloud target -r eu-de
```
{: pre}

Para comprobar la ubicación en la que se encuentra actualmente, ejecute el mandato siguiente:

```
ibmcloud target
```
{: pre}

## Cambio de regiones mediante la API  

Para interactuar con la API regional a través de REST, dirija la solicitud al punto final de la API de la región en la que desea crear recursos. El punto final de la API de la región se muestra más arriba en la tabla. Además, puede encontrar el punto final disponible para las distintas regiones con el mandato siguiente:

```
ibmcloud is regions
```
{: pre}


Por ejemplo, para obtener la lista de las VPC de la región `us-sur`, ejecute el mandato siguiente:

```
curl https://us-south.iaas.cloud.ibm.com/v1/vpcs?version=2019-01-01 -H "Authorization: $iam_token"
```
{: pre}


## Zonas

Para obtener la lista de zonas disponibles para cada región, ejecute el mandato `ibmcloud is zones <region>`. Por ejemplo, para obtener la lista de zonas de la región `us-sur`, ejecute el mandato siguiente:

```
ibmcloud is zones us-south
```
{: pre}
