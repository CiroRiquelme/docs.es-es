---
ms.openlocfilehash: c10d617e07ca2fa0239298d449d93cf833b83fce
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81274984"
---
### <a name="calls-to-claimsidentity-constructors"></a>Llamadas a los constructores de ClaimsIdentity

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.6.2, hay un cambio en el modo en que los constructores <xref:System.Security.Claims.ClaimsIdentity> con un parámetro <xref:System.Security.Principal.IIdentity?displayProperty=name> establecen la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name>. Si el argumento <xref:System.Security.Principal.IIdentity?displayProperty=name> es un objeto <xref:System.Security.Claims.ClaimsIdentity> y la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> de ese objeto <xref:System.Security.Claims.ClaimsIdentity> no es <code>null</code>, la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> se conecta mediante el método <xref:System.Security.Claims.ClaimsIdentity.Clone>. En .NET Framework 4.6.1 y versiones anteriores, la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> se adjuntaba como una referencia existente. Debido a este cambio, a partir de .NET Framework 4.6.2, la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> del nuevo objeto <xref:System.Security.Claims.ClaimsIdentity> no es igual que la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=name> del argumento <xref:System.Security.Principal.IIdentity?displayProperty=name> del constructor. En .NET Framework 4.6.1 y versiones anteriores, es igual.|
|Sugerencia|Si no desea este comportamiento, puede restaurar el comportamiento anterior si establece el modificador <code>Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity</code> en el archivo de configuración de la aplicación en <code>true</code>. Para ello, es necesario agregar lo siguiente a la sección <code>&lt;runtime&gt;</code> del archivo web.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.6.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity)></li><li><xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim})></li><li><xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim},System.String,System.String,System.String)></li></ul>|
