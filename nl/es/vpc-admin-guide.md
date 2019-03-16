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
{:download: .download}
{:DomainName: data-hd-keyref="DomainName"}

# Asignación de acceso basado en roles a recursos de VPC
{: #assigning-role-based-access-to-vpc-resources}

Los administradores de cuentas pueden utilizar _políticas_ de autorización, que controlan el acceso a _recursos_ en función del _rol_ de un usuario individual. Las políticas también se pueden aplicar para:

(1) la autorización de un grupo de usuarios, denominado _grupo de acceso_,

(2) en las características asignadas de un solo _recurso_, o

(3) en una colección de recursos denominado _grupo de recursos_.

Las autorizaciones correspondiente a recursos y las autorizaciones correspondientes a usuarios se pueden asignar de forma independiente.

Para obtener más información sobre la creación de usuarios, grupos de acceso de usuario, grupos de recursos y políticas, consulte [Acerca de los recursos](/docs/infrastructure/vpc?topic=vpc-about-vpc-infrastructure-resources).

## Control de accesos basado en IAM

En general, la autorización de {{site.data.keyword.cloud}} Virtual Private Cloud y las prácticas de gestión de recursos se coordinan con los servicios de IBM Cloud Identity and Access Management (IAM). Para obtener más información sobre IAM, los grupos de recursos y los grupos de acceso en general, consulte estos documentos de IBM Cloud:

* [IBM Cloud IAM](https://{DomainName}/docs/iam/quickstart.html#getstarted)
* [Grupos de recursos](https://{DomainName}/docs/overview/resource-groups.html#whatis)
* [Grupos de acceso](https://{DomainName}/docs/overview/manageaccess.html#cloudaccess)

Algunas características del servicio IAM de IBM Cloud se han personalizado para su uso en IBM Cloud VPC. El documento [Acerca de los recursos](/docs/infrastructure/vpc?topic=vpc-about-vpc-infrastructure-resources) contiene más información sobre las políticas de autorización de IAM y su aplicación en VPC.

En resumen, puede asignar autorizaciones basadas en IAM basándose en:

* usuarios individuales
* grupos de acceso (grupos de usuarios)
* tipos específicos de recursos
* grupos de recursos

## Asignación de permisos de usuario

Para los usuarios, el acceso se controla mediante la asignación de roles de IAM definidos por el sistema:

* Administrador
* Editor
* Operador
* Visor

En la tabla siguiente se muestra la correspondencia entre cada rol de usuario y el tipo de control que permite para las VPC:

| Nombre del rol | Tipo de acceso permitido |
|-----------|-------------------------|
| Visor | Ver VPC, listar VPC  |
| Editor | Ver VPC, listar VPC, crear VPC, suprimir VPC, actualizar VPC |
| Operador  | Ver VPC, listar VPC |
| Administrador |Ver VPC, listar VPC, crear VPC, suprimir VPC, actualizar VPC, asignar políticas a otros usuarios |


## Pasos siguientes

Para ver instrucciones paso a paso sobre cómo otorgar permisos basados en roles a los usuarios para determinadas tareas, consulte el tema sobre [Gestión de permisos de usuario para recursos de VPC](/docs/infrastructure/vpc?topic=vpc-managing-user-permissions-for-vpc-resources).
