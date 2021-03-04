---
title: Conceito de empresa no Dataverse
description: Este tópico descreve a integração de dados de empresa entre o Finance and Operations e o Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 2f0e3950f2b35dd8b8dbf50601b7d6b6d624863e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683666"
---
# <a name="company-concept-in-dataverse"></a>Conceito de empresa no Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]


No Finance and Operations, o conceito de *empresa* é uma construção legal e uma construção comercial. Ele também é um limite de segurança e de visibilidade de dados. Os usuários trabalham sempre no contexto de uma única empresa e a maioria dos dados são distribuídos por empresa.

O Dataverse não tem um conceito equivalente. O conceito mais próximo é *unidade de negócios*, que é basicamente um limite de segurança e de visibilidade para dados de usuário. Esse conceito não tem as mesmas implicações legais ou comerciais que o conceito de empresa.

Como a unidade de negócios e a empresa não são conceitos equivalentes, não é possível forçar um mapeamento linear (1:1) entre elas com a finalidade de integração do Dataverse. Porém, como os usuários devem, por padrão, ser capazes de ver as mesmas linhas no aplicativo e no Dataverse, a Microsoft apresentou uma nova entidade no Dataverse, chamada cdm\_Company. Essa entidade é equivalente à entidade Empresa no aplicativo. Para ajudar a garantir que a visibilidade das linhas seja imediatamente equivalente entre o aplicativo e o Dataverse, recomendamos a seguinte configuração para dados no Dataverse:

+ Para cada linha de empresa do Finance and Operations habilitado para gravação dupla, é criada uma linha cdm\_Company associada.
+ Quando uma linha cdm\_Company é criada e habilitada para gravação dupla, uma unidade de negócios padrão é criada com o mesmo nome. Embora uma equipe padrão seja criada automaticamente para essa unidade de negócios, a unidade de negócios não é usada.
+ Uma equipe de proprietário separada é criada com o mesmo nome. Ela também é associada à unidade de negócios.
+ Por padrão, o proprietário de qualquer linha criada e com gravação dupla no Dataverse é definido para a equipe "Proprietário DW" vinculada à unidade de negócios associada.

A ilustração a seguir mostra um exemplo dessa configuração de dados no Dataverse.

![Configuração de dados no Dataverse](media/dual-write-company-1.png)

Devido a essa configuração, qualquer linha relacionada à empresa USMF será propriedade de uma equipe que é vinculada à unidade de negócios USMF no Dataverse. Portanto, qualquer usuário que tenha acesso a essa unidade de negócios com uma função de segurança que é definida para visibilidade em nível de unidade de negócios agora pode consultar essas linhas. O exemplo a seguir mostra como as equipes podem ser usadas para oferecer o acesso correto a essas linhas.

+ A função "gerente de vendas" é atribuída aos membros da equipe de "Vendas USMF".
+ Os usuários com a função "Gerente de vendas" podem acessar quaisquer linhas da conta que seja membro da mesma unidade de negócios de que são membros.
+ A equipe "Vendas USMF" está vinculada à unidade de negócios de USMF citada anteriormente.
+ Assim, os membros da equipe "Vendas USMF" podem ver qualquer conta de propriedade do usuário "USMF DW", que viria da entidade Empresa USMF no Finance and Operations.

![Como as equipes podem ser usadas](media/dual-write-company-2.png)

Conforme mostrado na ilustração anterior, este mapeamento 1:1 entre unidade de negócios, empresa e equipe é apenas um ponto de partida. Neste exemplo, uma nova unidade de negócios “Europa” é criada manualmente no Dataverse como o pai de DEMF e ESMF. Essa nova unidade de negócios raiz não está relacionada à gravação dupla. No entanto, ela pode ser usada para dar aos membros da equipe de "Vendas BRL" acesso à dados de conta em DEMF e ESMF, definindo a visibilidade de dados como **BU pai/filho** na função de segurança associada.

Um tópico final para discutir é como a gravação dupla determina à qual equipe proprietária deve-se atribuir linhas. Esse comportamento é controlado pelo campo **Equipe proprietária padrão** do registro cdm\_Company. Quando uma linha cdm\_Company estiver habilitada para gravação dupla, um plug-in criará automaticamente a unidade de negócios associada e a equipe proprietária (se ainda não existir) e definirá o campo **Equipe proprietária padrão**. O administrador pode alterar este campo para um valor diferente. No entanto, o administrador não pode desmarcar o campo desde que a entidade esteja habilitada para gravação dupla.

> [!div class="mx-imgBorder"]
![Campo da equipe proprietária padrão](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Divisão e inicialização de empresa

A integração do Dataverse faz a paridade empresarial usando um identificador empresarial aos dados de tarja. Como a ilustração a seguir mostra, todas as tabelas específicas estão estendidas de forma que têm uma relação vários para um (N:1) com a entidade cdm\_Company.

> [!div class="mx-imgBorder"]
![A relação N:1 entre uma entidade específica de empresa e a entidade cdm_Company](media/dual-write-bootstrapping.png)

+ Para linhas, depois que uma empresa é adicionada e salva, torna-se o valor somente leitura. Portanto, os usuários devem garantir selecionam a empresa correta.
+ Somente linhas com dados da empresa estão qualificados para gravação dupla entre o aplicativo e o Dataverse.
+ Para dados existentes do Dataverse, uma experiência de inicialização conduzida pelo administrador logo estará disponível.


## <a name="autopopulate-company-name-in-customer-engagement-apps"></a>Preencher automaticamente o nome da empresa nos aplicativos de participação do cliente

Há várias maneiras de preencher automaticamente o nome da empresa nos aplicativos de participação do cliente.

+ Se você for um administrador de sistema, poderá definir a empresa padrão navegando até **Configurações Avançadas > Sistema > Segurança > Usuários**. Abra o formulário **Usuário** e na seção **Informações sobre a Organização**, defina o valor **Empresa como padrão nos Formulários**.

    :::image type="content" source="media/autopopulate-company-name-1.png" alt-text="Definir a empresa padrão na seção Informações da Organização.":::

+ Se tiver acesso de **Gravação** para a entidade **SystemUser** para o nível **Unidade de Negócio**, você poderá alterar a empresa padrão em qualquer formulário, selecionando a empresa do menu suspenso **Empresa**.

    :::image type="content" source="media/autopopulate-company-name-2.png" alt-text="Alterar o nome da empresa em uma nova conta.":::

+ Se tiver o acesso de **Gravação** para dados em mais de uma empresa, então você pode alterar a empresa padrão, escolhendo uma linhas que pertence a outra empresa.

    :::image type="content" source="media/autopopulate-company-name-3.png" alt-text="A escolha de uma linha altera a empresa padrão.":::

+ Se você for um configurador de sistema ou administrador e quiser preencher automaticamente os dados da empresa em um formulário personalizado, poderá usar os [eventos do formulário](https://docs.microsoft.com/powerapps/developer/model-driven-apps/clientapi/events-forms-grids). Adicione uma referência JavaScript ao **msdyn_/DefaultCompany.js** e use os eventos a seguir. Você pode usar qualquer formulário predefinido, por exemplo, o formulário **Conta**.

    + Evento **OnLoad** do formulário: Defina o campo **defaultCompany**.
    + Evento **OnChange** para o campo **Empresa**: Defina o campo **updateDefaultCompany**.

## <a name="apply-filtering-based-on-the-company-context"></a>Aplicar filtrar com base no contexto da empresa

Para aplicar filtragem com base no contexto da empresa nos formulários personalizados ou em campos de pesquisa personalizados adicionados aos formulários padrão, abra o formulário e use a seção **Filtragem de Registros Relacionados** para aplicar o filtro da empresa. Você deve definir isso para cada campo de pesquisa que exija filtragem com base na empresa subjacente em uma determinada linha. A configuração é mostrada para a **Conta** na ilustração a seguir.

:::image type="content" source="media/apply-company-context.png" alt-text="Aplicar contexto da empresa":::



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]