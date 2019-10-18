---
title: Conceito de empresa no Common Data Service
description: Este tópico descreve a integração de dados de empresa entre o Finance and Operations e o Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: aa4d54fd7b3ab407751ad6ca1032d742c23eed41
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184522"
---
## <a name="company-concept-in-common-data-service"></a>Conceito de empresa no Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

No Finance and Operations, o conceito de *empresa* é um conceito legal e um conceito comercial. Ele também é um limite de segurança e de visibilidade de dados. Os usuários trabalham sempre no contexto de uma única empresa e a maioria dos dados são distribuídos por empresa.

O Common Data Service não tem um conceito equivalente. O conceito mais próximo é *unidade de negócios*, que é basicamente um limite de segurança e de visibilidade para dados de usuário. Esse conceito não tem as mesmas implicações legais ou comerciais que o conceito de empresa.

Como a unidade de negócios e a empresa não são conceitos equivalentes, não é possível forçar um mapeamento linear (1:1) entre elas com a finalidade de integração do Common Data Service. Porém, como os usuários devem, por padrão, ser capazes de ver os mesmos registros no aplicativo e no Common Data Service, a Microsoft apresentou uma nova entidade no Common Data Service, chamada cdm\_Company. Essa entidade é equivalente à entidade Empresa no aplicativo. Para ajudar a garantir que a visibilidade dos registros seja imediatamente equivalente entre o aplicativo e o Common Data Service, recomendamos a seguinte configuração para dados no Common Data Service:

+ Para cada registro de empresa do Finance and Operations que é habilitado para gravação dupla, é criado um registro associado cdm\_Company.
+ Quando um registro cdm\_Company é criado e habilitado para gravação dupla, uma unidade de negócios padrão é criada com o mesmo nome. Embora uma equipe padrão seja criada automaticamente para essa unidade de negócios, a unidade de negócios não é usada.
+ Uma equipe de proprietário separada é criada com o mesmo nome. Ela também é associada à unidade de negócios.
+ Por padrão, o proprietário de qualquer registro criado e com gravação dupla no Common Data Service é definido para a equipe "Proprietário DW" vinculada à unidade de negócios associada.

A ilustração a seguir mostra um exemplo dessa configuração de dados no Common Data Service.

![Configuração de dados no Common Data Service](media/dual-write-company-1.png)

Devido a essa configuração, qualquer registro relacionado à empresa USMF será propriedade de uma equipe que é vinculada à unidade de negócios USMF no Common Data Service. Portanto, qualquer usuário que tenha acesso a essa unidade de negócios com uma função de segurança que é definida para visibilidade em nível de unidade de negócios agora pode consultar esses registros. O exemplo a seguir mostra como as equipes podem ser usadas para oferecer o acesso correto a esses registros.

+ A função "gerente de vendas" é atribuída aos membros da equipe de "Vendas USMF".
+ Os usuários com a função "Gerente de vendas" podem acessar qualquer registro de conta que seja membro da mesma unidade de negócios de que são membros.
+ A equipe "Vendas USMF" está vinculada à unidade de negócios de USMF citada anteriormente.
+ Portanto, os membros da equipe "Vendas USMF" podem ver qualquer conta que seja de propriedade do usuário "USMF DW", que viria da entidade Empresa USMF no Finance and Operations.

![Como as equipes podem ser usadas](media/dual-write-company-2.png)

Conforme mostrado na ilustração anterior, este mapeamento 1:1 entre unidade de negócios, empresa e equipe é apenas um ponto de partida. Neste exemplo, uma nova unidade de negócios “Europa” é criada manualmente no Common Data Service como o pai de DEMF e ESMF. Essa nova unidade de negócios raiz não está relacionada à gravação dupla. No entanto, ela pode ser usada para dar aos membros da equipe de "Vendas BRL" acesso à dados de conta em DEMF e ESMF, definindo a visibilidade de dados como **BU pai/filho** na função de segurança associada.

Um tópico final para discutir é como a gravação dupla determina à qual equipe proprietária deve-se atribuir registros. Esse comportamento é controlado pelo campo **Equipe proprietária padrão** do registro cdm\_Company. Quando um registro cdm\_Company estiver habilitado para gravação dupla, um plug-in criará automaticamente a unidade de negócios associada e a equipe proprietária (se ainda não existir) e definirá o campo **Equipe proprietária padrão**. O administrador pode alterar este campo para um valor diferente. No entanto, o administrador não pode desmarcar o campo desde que a entidade esteja habilitada para gravação dupla.

![Campo da equipe proprietária padrão](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Divisão e inicialização de empresa

A integração do Common Data Service faz a paridade empresarial usando um identificador empresarial aos dados de tarja. Como a ilustração a seguir mostra, todas as entidades específicas estão estendidas de forma que têm uma relação vários para um (N:1) com a entidade cdm\_Company.

![A relação N:1 entre uma entidade específica de empresa e a entidade cdm_Company](media/dual-write-bootstrapping.png)

+ Para registros, depois que uma empresa é adicionada e salva, torna-se o valor somente leitura. Portanto, os usuários devem garantir selecionam a empresa correta.
+ Somente os registros com dados da empresa estão qualificados para gravação dupla entre o aplicativo e o Common Data Service.
+ Para dados existentes do Common Data Service, uma experiência de inicialização conduzida pelo administrador logo estará disponível.
