---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 6e78275aaeb202405e327302455d56fa431d7f27
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855249"
---
# <a name="filter"></a>\<filter>

Define un filtro de enrutamiento, que determina el tipo de Windows Communication Foundation (WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> ) que se va a usar al evaluar los mensajes entrantes, así como cualquier dato o parámetro auxiliar requerido por el filtro.

[ **\<system.serviceModel>** ](system-servicemodel.md)\
&nbsp;&nbsp;[ **\<> de enrutamiento**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de filtros**](filters-of-routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<filtrar >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<routing>
  <filters>
    <filter customType="String"
            filterData="String"
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
            name="String" />
  </filters>
</routing>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

| Atributo  | DESCRIPCIÓN |
| ---------- | ----------- |
| customType | Cadena que contiene el nombre de tipo completo del tipo personalizado que se va a usar como filtro. Si `filterType` está establecido en `custom`, este atributo contiene el nombre de tipo completo de la clase que se va a crear.  `filterData`también puede contener valores que se van a usar durante la evaluación del filtro de tipo personalizado. |
| filterData | Cadena que contiene los datos del filtro. Para obtener más información sobre cómo especificar este atributo, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| filterType | Cadena que contiene el tipo de filtro. Este atributo es del tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.  Para obtener más información sobre su funcionamiento con el atributo `filterData`, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| name       | Cadena que contiene el nombre único de este elemento de filtro. |

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

| Elemento | DESCRIPCIÓN |
| ------- | ----------- |
| [\<> de enrutamiento](routing.md) | Sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation<xref:System.ServiceModel.Dispatcher.MessageFilter> (WCF) que se va a usar al evaluar los mensajes entrantes. |

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
