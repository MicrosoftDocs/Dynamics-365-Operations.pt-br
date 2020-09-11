---
title: Conceito de empresa no Common Data Service
description: Este tópico descreve a integração de dados de empresa entre o Finance and Operations e o Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 08/04/2020
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
ms.openlocfilehash: 444bfc1698a206ca34e67f742df63431a3b02649
ms.sourcegitcommit: 7da8811f1a7db858efb76edb0bdf857a47d07600
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2020
ms.locfileid: "3728404"
---
# <a name="company-concept-in-common-data-service"></a>Conceito de empresa no Common Data Service

[!include [banner](../../includes/banner.md)]


No Finance and Operations, o conceito de *empresa* é uma construção legal e uma construção comercial. Ele também é um limite de segurança e de visibilidade de dados. Os usuários trabalham sempre no contexto de uma única empresa e a maioria dos dados são distribuídos por empresa.

O Common Data Service não tem um conceito equivalente. O conceito mais próximo é *unidade de negócios*, que é basicamente um limite de segurança e de visibilidade para dados de usuário. Esse conceito não tem as mesmas implicações legais ou comerciais que o conceito de empresa.

Como a unidade de negócios e a empresa não são conceitos equivalentes, não é possível forçar um mapeamento linear (1:1) entre elas com a finalidade de integração do Common Data Service. Porém, como os usuários devem, por padrão, ser capazes de ver os mesmos registros no aplicativo e no Common Data Service, a Microsoft apresentou uma nova entidade no Common Data Service, chamada cdm\_Company. Essa entidade é equivalente à entidade Empresa no aplicativo. Para ajudar a garantir que a visibilidade dos registros seja imediatamente equivalente entre o aplicativo e o Common Data Service, recomendamos a seguinte configuração para dados no Common Data Service:

+ Para cada registro de empresa do Finance and Operations habilitado para gravação dupla, é criado um registro cdm\_Company associado.
+ Quando um registro cdm\_Company é criado e habilitado para gravação dupla, uma unidade de negócios padrão é criada com o mesmo nome. Embora uma equipe padrão seja criada automaticamente para essa unidade de negócios, a unidade de negócios não é usada.
+ Uma equipe de proprietário separada é criada com o mesmo nome. Ela também é associada à unidade de negócios.
+ Por padrão, o proprietário de qualquer registro criado e com gravação dupla no Common Data Service é definido para a equipe "Proprietário DW" vinculada à unidade de negócios associada.

A ilustração a seguir mostra um exemplo dessa configuração de dados no Common Data Service.

![Configuração de dados no Common Data Service](media/dual-write-company-1.png)

Devido a essa configuração, qualquer registro relacionado à empresa USMF será propriedade de uma equipe que é vinculada à unidade de negócios USMF no Common Data Service. Portanto, qualquer usuário que tenha acesso a essa unidade de negócios com uma função de segurança que é definida para visibilidade em nível de unidade de negócios agora pode consultar esses registros. O exemplo a seguir mostra como as equipes podem ser usadas para oferecer o acesso correto a esses registros.

+ A função "gerente de vendas" é atribuída aos membros da equipe de "Vendas USMF".
+ Os usuários com a função "Gerente de vendas" podem acessar qualquer registro de conta que seja membro da mesma unidade de negócios de que são membros.
+ A equipe "Vendas USMF" está vinculada à unidade de negócios de USMF citada anteriormente.
+ Assim, os membros da equipe "Vendas USMF" podem ver qualquer conta de propriedade do usuário "USMF DW", que viria da entidade Empresa USMF no Finance and Operations.

![Como as equipes podem ser usadas](media/dual-write-company-2.png)

Conforme mostrado na ilustração anterior, este mapeamento 1:1 entre unidade de negócios, empresa e equipe é apenas um ponto de partida. Neste exemplo, uma nova unidade de negócios “Europa” é criada manualmente no Common Data Service como o pai de DEMF e ESMF. Essa nova unidade de negócios raiz não está relacionada à gravação dupla. No entanto, ela pode ser usada para dar aos membros da equipe de "Vendas BRL" acesso à dados de conta em DEMF e ESMF, definindo a visibilidade de dados como **BU pai/filho** na função de segurança associada.

Um tópico final para discutir é como a gravação dupla determina à qual equipe proprietária deve-se atribuir registros. Esse comportamento é controlado pelo campo **Equipe proprietária padrão** do registro cdm\_Company. Quando um registro cdm\_Company estiver habilitado para gravação dupla, um plug-in criará automaticamente a unidade de negócios associada e a equipe proprietária (se ainda não existir) e definirá o campo **Equipe proprietária padrão**. O administrador pode alterar este campo para um valor diferente. No entanto, o administrador não pode desmarcar o campo desde que a entidade esteja habilitada para gravação dupla.

> [!div class="mx-imgBorder"]
![Campo da equipe proprietária padrão](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Divisão e inicialização de empresa

A integração do Common Data Service faz a paridade empresarial usando um identificador empresarial aos dados de tarja. Como a ilustração a seguir mostra, todas as entidades específicas estão estendidas de forma que têm uma relação vários para um (N:1) com a entidade cdm\_Company.

> [!div class="mx-imgBorder"]
![A relação N:1 entre uma entidade específica de empresa e a entidade cdm_Company](media/dual-write-bootstrapping.png)

+ Para registros, depois que uma empresa é adicionada e salva, torna-se o valor somente leitura. Portanto, os usuários devem garantir selecionam a empresa correta.
+ Somente os registros com dados da empresa estão qualificados para gravação dupla entre o aplicativo e o Common Data Service.
+ Para dados existentes do Common Data Service, uma experiência de inicialização conduzida pelo administrador logo estará disponível.


## <a name="autopopulate-company-name-in-customer-engagement-apps"></a>Preencher automaticamente o nome da empresa nos aplicativos de participação do cliente

Há várias maneiras de preencher automaticamente o nome da empresa nos aplicativos de participação do cliente.

+ Se você for um administrador de sistema, poderá definir a empresa padrão navegando até **Configurações Avançadas > Sistema > Segurança > Usuários**. Abra o formulário **Usuário** e na seção **Informações sobre a Organização**, defina o valor **Empresa como padrão nos Formulários**.

    :::image type="content" source="media/autopopulate-company-name-1.png" alt-text="Definir a empresa padrão na seção Informações da Organização.":::

+ Se tiver acesso de **Gravação** para a entidade **SystemUser** para o nível **Unidade de Negócio**, você poderá alterar a empresa padrão em qualquer formulário, selecionando a empresa do menu suspenso **Empresa**.

    :::image type="content" source="media/autopopulate-company-name-2.png" alt-text="Alterar o nome da empresa em uma nova conta.":::

+ Se tiver o acesso de **Gravação** para dados em mais de uma empresa, então você pode alterar a empresa padrão, escolhendo um registro que pertence a outra empresa.

    :::image type="content" source="media/autopopulate-company-name-3.png" alt-text="A escolha de um registro altera a empresa padrão.":::

+ Se você for um configurador de sistema ou administrador e quiser preencher automaticamente os dados da empresa em um formulário personalizado, poderá usar os [eventos do formulário](https://docs.microsoft.com/powerapps/developer/model-driven-apps/clientapi/events-forms-grids). Adicione uma referência JavaScript ao **msdyn_/DefaultCompany.js** e use os eventos a seguir. Você pode usar qualquer formulário predefinido, por exemplo, o formulário **Conta**.

    + Evento **OnLoad** do formulário: Defina o campo **defaultCompany**.
    + Evento **OnChange** para o campo **Empresa**: Defina o campo **updateDefaultCompany**.

## <a name="apply-filtering-based-on-the-company-context"></a>Aplicar filtrar com base no contexto da empresa

Para aplicar filtragem com base no contexto da empresa nos formulários personalizados ou em campos de pesquisa personalizados adicionados aos formulários padrão, abra o formulário e use a seção **Filtragem de Registros Relacionados** para aplicar o filtro da empresa. Você deve definir isso para cada campo de pesquisa que exija filtragem com base na empresa subjacente em um determinado registro. A configuração é mostrada para a **Conta** na ilustração a seguir.

:::image type="content" source="media/apply-company-context.png" alt-text="Aplicar contexto da empresa":::

