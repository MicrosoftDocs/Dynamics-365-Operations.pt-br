---
title: "Espaço de trabalho móvel de controle de custos para o aplicativo do Microsoft Dynamics 365 for Operations"
description: "Com o espaço de trabalho móvel de controle de custos, os gerentes de centro de custo podem ver o desempenho do centro de custo a qualquer momento e em qualquer lugar."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 53 - 04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 84740472-494f-444c-9b74-f83b7342fd25
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 8136efb1d2669c39fcc0f80b60e80ecae983d5d8
ms.lasthandoff: 03/31/2017


---

# <a name="cost-controlling-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Espaço de trabalho móvel de controle de custos para o aplicativo do Microsoft Dynamics 365 for Operations

Com o espaço de trabalho móvel de controle de custos, os gerentes de centro de custo podem ver o desempenho do centro de custo a qualquer momento e em qualquer lugar. 

<a name="prerequisites"></a>Pré-requisitos
-------------

| Pré-requisito                                                         | descrição                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Leia sobre a plataforma móvel do Microsoft Dynamics 365 for Operations | [Plataforma móvel do Microsoft Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 for Operations                                          | Verifique se você está usando um ambiente com a versão 1611 do Microsoft Dynamics 365 for Operations e a atualização 3 da plataforma do Microsoft Dynamics for Operations (novembro de 2016). |
| Hotfix KB 3215650                                                    | Instale o hotfix para habilitar os espaços de trabalho que são fornecidos no Microsoft Dynamics 365 for Operations.                                                                       |
| Dispositivo móvel com o Dynamics 365 for Operations instalado | Baixe o aplicativo do Dynamics 365 for Operations na sua loja de aplicativos móveis.                                                                                                      |

## <a name="introduction"></a>Introdução
O espaço de trabalho móvel de controle de custos fornece uma exibição instantânea do desempenho atual dos centros de custo comparando custos reais com os custos orçados. Você pode fazer uma busca detalhada nos status de elementos de custo individuais.

### <a name="example"></a>Exemplo

Um funcionário recebe um convite para uma conferência internacional. A organização terá que cobrir todas as despesas da viagem. O funcionário pergunta a seu gerente se pode participar da conferência. O gerente abre rapidamente o espaço de trabalho móvel de controle de custos no seu telefone móvel para ver se dispõe do orçamento para que o funcionário possa ir à conferência.

### <a name="data-security"></a>Segurança de dados

Os dados no espaço de trabalho de controle de custos são protegidos pelas credenciais do usuário. Um gerente de centro de custo só pode ver dados de seu próprio centro de custo. A segurança de nível de acesso é gerenciada dentro do módulo de contabilização de custos. Os contadores definem a configuração do espaço de trabalho móvel de controle de custos no módulo de contabilização de custos. Após a publicação do espaço de trabalho no aplicativo do Microsoft Dynamics 365 for Operations, ele fica disponível no aplicativo móvel do Dynamics 365 for Operations. Com isso, todos os gerentes de centro de custo na organização podem ver os dados no mesmo formato.

### <a name="actions-views-and-links"></a>Ações, exibições e links

O espaço de trabalho móvel de controle de custos para o aplicativo do Dynamics 365 for Operations fornece estas ações, exibições e links:

-   Ações 
    -   Selecione **Configurações** para escolher um layout.
    -   Selecione **Objetos de custo** para escolher centros de custo nos quais você deseja filtrar dados. **Observação:** a lista é exibida de acordo com o acesso concedido no módulo de contabilização de custos.

<!-- -->

-   Com base no que é selecionado em **Ações** e no que é configurado no módulo de contabilização de custos, você pode exibir as seguintes informações nos cartões. Observe que o valor é exibido no mesmo formato: real, orçamento, variação e variação em %. 
    -   Real vs. orçamento (período atual)
    -   Real vs. orçamento revisado (período atual)
    -   Real vs. orçamento (período anterior)
    -   Real vs. orçamento revisado (período anterior)
    -   Real vs. orçamento (ano até a data)
    -   Real vs. orçamento revisado (ano até a data)

<!-- -->

-   Links
    -   Detalhes do período atual.
    -   Detalhes do período anterior.
    -   Detalhes do ano até a data.

Quando você seleciona um dos links, um cartão por elemento de custo é exibido. O valor nos cartões é exibido no seguinte formato: real, orçamento, variação de orçamento, variação de orçamento em %, orçamento revisado, variação do orçamento revisado e variação de orçamento revisado em %.  [![cost-controlling](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="get-started"></a>Introdução
Siga estas etapas para começar a usar o aplicativo móvel de controle de custos no seu dispositivo móvel.

1.  Na sua loja de aplicativos móveis, baixe e instale o aplicativo do Microsoft Dynamics 365 for operations.
2.  Inicie o aplicativo no seu dispositivo.
3.  Insira sua URL do Dynamics 365.
4.  Insira a empresa à qual deseja se conectar. Por exemplo, insira **USMF**.
5.  No primeiro acesso, são solicitados nome de usuário e senha da sua conta do Microsoft Dynamics 365 for Operations. Insira suas credenciais. Após se conectar, você verá os espaços de trabalho da sua empresa.

Para exibir os espaços de trabalho no seu aplicativo móvel, primeiro você deve publicar os espaços de trabalho desejados para o aplicativo do Dynamics 365 for Operations.

1.  Inicie o Dynamics 365 for Operations.
2.  Vá para **Administração do sistema** &gt; **Configuração** &gt; **Parâmetros do sistema**.
3.  Selecione o **Gerenciar aplicativo móvel**.
4.  Selecione o espaço de trabalho **Controle de custo** para publicar a plataforma móvel.
5.  Selecione **Publicar espaço de trabalho**.
6.  Atualize seu dispositivo para ver os espaços de trabalho publicados.

## <a name="view-the-performance-of-your-cost-center"></a>Exibir o desempenho do seu centro de custo
1.  No seu dispositivo móvel, selecione o espaço de trabalho **Controle de custo**.
2.  Selecione **Controle de objeto de custo**.
3.  Clique em **Ações**.
4.  Clique em **Selecionar configuração** para selecionar um layout de controle de custos.
5.  Clique em **Concluído**.
6.  Clique em **Ações**.
7.  Clique em **Selecionar objeto de custo** para selecionar os centros de custo aos quais você tem acesso.
8.  Clique em **Concluído**.
9.  Exiba o desempenho geral do seu centro de custo.
10. Clique em **Detalhes do período atual**.
11. Exiba o desempenho dos elementos de custo individuais.
12. Você também pode pesquisar elementos de custo específicos.



